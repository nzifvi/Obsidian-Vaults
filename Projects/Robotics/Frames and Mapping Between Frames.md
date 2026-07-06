2 frames exist: a global and local frame.
- The local frame is relative to the global frame.

- Let $F_{\text{G}}$ denote the global frame.
- Let $F_{\text{L}}$ denote the local frame.

$$
F_{\text{G}} = \{X_{\text{G}}, Y_{\text{G}} \}
$$
$$
F_{\text{L}} = \{X_{\text{L}}, Y_{\text{L}}\}
$$

A pose vector denotes a robot's position, and orientation, with respect to a frame.

$$
\vec{\xi}_{\text{G}} = \begin{bmatrix}x_G\\y_G\\\theta\end{bmatrix}
$$
Where...
- (x, y) is the position with respect to reference point P.
- $\theta$ is the angle between the global and local frame.

One pose vector is possible for each frame.
- A local pose vector, $\vec{\xi}_L$, can be mapped to a global pose vector using orthogonal rotation matrix $R(\theta)$

$$
\vec{\xi}_F = R(\theta)\vec{\xi}_R
$$
$$
\vec{\xi}_G = R(\theta)^{-1}\vec{\xi}_F
$$


