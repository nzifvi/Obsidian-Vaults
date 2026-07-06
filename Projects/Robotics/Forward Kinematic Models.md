
---
# Modelling of a Wheeled Differential-Drive Robot
A Differential-Drive robot has 2 wheels.
- If it has 4 wheels, the wheels on the same side are modelled as 1 since they will always have the same angular velocity.

A differential-drive has 2 wheels. Each...
- has diameter $d$.
- has a distance $l$ to the centre of the robot $P$.
- Each has an angular velocity: $\phi_{L}, \phi_{R}$

If $\vec{\xi}_G$ denotes the position and bearing with respects to the global frame...
$$
\frac{d\vec{\xi}_G}{dt} = \begin{bmatrix}\frac{dx}{dt} \\ \frac{dy}{dt} \\ \frac{d\theta}{dt} \end{bmatrix}
$$
... denotes the VELOCITY and rate of bearing change with respects to the global frame...

$\frac{d\vec{\xi}_G}{dt}$ is a function of f
$$
f(l, r, \theta, \phi_L, \phi_R)
$$

A wheel, with an angular velocity $\phi$, has a linear velocity of $r\phi$. Since $P$ is halfway between the 2 wheels, each wheel contributes HALF it's linear velocity to translation at point P.
$$
\frac{dx(\phi)}{dt} = \frac{1}{2}r\phi
$$
$$
\frac{dx_R}{dt} = \frac{dx(\phi_L)}{dt}+\frac{dx(\phi_R)}{dt}
$$
- NOTE: if it is impossible for a wheel to achieve lateral motion, $\frac{dy_R}{dt}$ = 0

This can be used to calculate the rotation of a robot given a knowledge of applied angular velocities to the wheels.
$$
\omega_L = \frac{r\phi_L}{2l}
$$
$$
\omega_R = \frac{r\phi_R}{2l}
$$
