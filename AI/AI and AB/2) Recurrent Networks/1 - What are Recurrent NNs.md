[[2,1 - Time Series, Phase Plane]] $\leftarrow$ Next

---
# What are Recurrent NNs?
Recurrent NNs are bi-directional, multi-layered neural networks.
- Some neurons may be connected to neurons in the prior layer.
- Brains are not just a feed-forward NN, they are highly recurrent (feedback loops)

![[Pasted image 20260204213527.png]]

$$
\vec{y}(t)= g\biggr(W\vec{I}(t)+\vec{\theta}\biggr)
$$
$$
\vec{y}(t+1)=g\biggr(W\vec{y(t)}+\vec{I}(t+1)+\vec{\theta}\biggr)
$$

In RNNs, there are...
1) Weights Matrix: $W$
$$
W_{N^2}
$$
- N neurons in the RNN.

2) The Biases: $\vec{\theta}$

$$
\vec{\theta}_{N\cdot 1}=\begin{bmatrix}\theta_1\\...\\\theta_N\end{bmatrix}
$$
1) Impulse Vector: $\vec{I}(t)$ at time t.
	- Inputs are a function of time. The inputs to the RNN may differ between points in time.

$$
\vec{I}_{N\cdot1}(t)=\begin{bmatrix}I_1\\...\\I_N\end{bmatrix}
$$
- Value of $\vec{I}(t)$ depends on time t. 
	- Each time t determines if $\vec{I}(t)$ is a zeros vector or not.
	- The pulse time, $t_{pulse}$ is a specified value.
	- Each pulse has a duration, $pulse_{duration}$, which is specified and determines how long a pulse lasts for.

$$
t \geq t_{pulse} \wedge t\leq t_{pulse}+pulse_{duration} \Rightarrow \vec{I}(t) \cancel{=} \vec{0}
$$
$$
t \leq t_{pulse} \lor t > t_{pulse}+pulse_{duration} \Rightarrow \vec{I}(t)
 = \vec{0}$$

2) Outputs at time t: $\vec{y}(t)$
	- In RNN, the output is the output of the ENTIRE model at time t.
	- NOT output at a layer.
$$
\vec{y}(t)=\begin{bmatrix}y_1(t)\\...\\y_n(t)\end{bmatrix}
$$

# Forward-Prop in RNNs
Rather than calculating outputs per layer, a forward prop is calculating the output of the ENTIRE RNN at time t.
- $\vec{y}(t)$ referred to as state of RNN at time t.

Must differentiate between points in time:
- $t=1$ - INITIAL STATE, use formula:
$$
\vec{y}(t)=g\biggr(W\vec{I} + \vec{\theta}\biggr)
$$
- $t>1$ - NON-INITIAL STATE, use formula:
$$
\vec{y}(t+1)=g\biggr(W\vec{y}(t)+\vec{I}+\vec{\theta}\biggr)
$$