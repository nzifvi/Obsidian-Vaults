
---
# 1) What are KFs?
KFs are a model which can be used to predict the parameters, states, or inputs of a system.

Inputs to a system are sometimes noisy or inaccurate.
- Noisy/inaccurate inputs make the outputs of a system worse.
- KF predicts input values, given an input value and a history of inputs.
- KFs estimates inputs with great accuracy in real time.


KFs are useful for...
1) Filtering the outputs of a sensor before fed to the system as inputs.

# 2) KF Mathematic Components
Where a system has m inputs and n outputs...
- $\vec{x}_{n\times 1}$ is the state variable.
	-  What is being estimated.
- $P_{n^2}$ is the state covariance matrix.
	- Represents KF's uncertainty in the estimation of $\vec{x}(t)$
- $\vec{z}_{m\times 1}$ is the measurement vector.
	- The measurement vector which may be inaccurate/noisy.
	- The ONLY real-world info KFs receive.
- $A_{n^2}$ is the state transition matrix.
	- 
- $H_{m\times n}$ is the state-to-measurement matrix.
	- Maps from state space to measurement space.
	- Answers: given a true, correct state $\vec{x}(t)$, what measurement $\vec{z}$ would be produced.
- $R_{m^2}$ is the measurement covariance matrix.
	- Represents uncertainty in the source of the measurements.
- $Q_{n^2}$ is the process noise covariance matrix.
- $K_{n\times m}$ is the Kalman gain.
	- Determines whether the measurement, or prediction, is trusted.



# 3) Steps
KF has 2 main steps: predict and update
- Each step has sub-steps.
## 3.1) Predict
Using the previously estimated state variable and state covariance matrix, predict the next state variable and state covariance matrix.

Predict state consists of...
1) State variable prediction.
2) State covariance matrix prediction.

$$
\vec{x}(t+1 | t) = A\vec{x}(t|t)
$$

$$
P(t+1|t) = AP(t|t)A^T + Q
$$




# 4) Static vs Dynamic KF
If a previously recorded state variable, $\vec{x}$, can have different values when observed AGAIN, the model must be dynamic.
- Otherwise, it can be static.

KF being static or dynamic massively changes the components of a KF.

## 2.2.1) Static KF
ASSUMPTION: previously observed state variables do not change.

$$
\vec{x}(t+\Delta t)=A\vec{x}(t)
$$


## 2.2.2) Dynamic KF



# Example
Suppose a KF is applied to the outputs of a LiDAR sensor
- LiDAR outputs 3 values: x-ordinate, y-ordinate, and z-ordinate.

Each outputted measurement, $\vec{z}$, is a function of time t.
$$
\vec{z}(t) =\begin{bmatrix}
x(t)\\
y(t)\\
z(t)
\end{bmatrix}
$$
$$
R(t)=\begin{bmatrix}
\sigma^2_x(t) & \sigma_{xy}(t) & \sigma_{xz}(t)\\
\sigma_{yx}(t) & \sigma^2_y(t) & \sigma_{yz}(t)\\
\sigma_{zx}(t) & \sigma_{zy}(t) & \sigma^2_{z}(t)
\end{bmatrix}
$$
Suppose the goal of the KF is to just reduce the noise in the measurements from the sensor.
- $n = 3$
- NOTE: KF can be used to estimate more states which are not directly observed.

$$
\vec{x}(t)=\begin{bmatrix}
x(t)\\
y(t)\\
z(t)\\
\end{bmatrix}
$$
$$
P(t)=\begin{bmatrix}
\sigma^2_x(t) & \sigma_{xy}(t) & \sigma_{xz}(t)\\
\sigma_{yx}(t) & \sigma^2_y(t) & \sigma_{yz}(t)\\
\sigma_{zx}(t) & \sigma_{zy}(t) & \sigma^2_{z}(t)
\end{bmatrix}
$$
ASSUMPTION: true position, of each point, does not change over time.
- The sensor is static and the environment about it is also static.

$$
A = I_{3^2}= \begin{bmatrix}
1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 1
\end{bmatrix}
$$

$$
A=I_{3^2} \Rightarrow \vec{x}(t+1)=A\vec{x}(t) = \vec{x}(t)
$$