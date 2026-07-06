[[2,1 - Gaussian Injection]] $\leftarrow$ Back

---
# Problem
Given a 2D frame, where each element is a distance, and a 3D population of neurons, do Gaussian injection into the 3D neuron population.

$$
D_{M\times N} = \begin{bmatrix}
d_{1,1} & ... & d_{1, M} \\
\vdots  & \ddots & \vdots \\
d_{N,1} & ... & d_{N,M}
\end{bmatrix}
$$
Problem:
- 3D neuron indices exist in tuning space. Each neuron has a...
	- Preferred egocentric azimuth
	- Preferred egocentric elevation
	- Preferred distance.
- Must map (i, j, $d_{i, j}$) to $(\theta_{e}, \phi_{e}, d_{i, j})$

Let...
- $f_x, f_y$ are the focal lengths in pixels.
	- Derived from the focal length $f$
$$
f_x = \frac{f}{s_x}, f_y =\frac{f}{s_y}
$$
- $c_x, c_y$ is the principal point
	- The principal point is the pixel coordinate, in an image, where the camera's optical axis intersects image plane
$$
(c_x, c_y) = \bigg(\frac{N}{2}, \frac{M}{2}\bigg)
$$

$$
\theta(j) = arctan\bigg(\frac{j-c_x}{f_x}\bigg)
$$
$$
\phi(i) = arctan\bigg(\frac{c_y-i}{f_y}\bigg)
$$
NOTE: $\theta(j) \cancel{=} \theta_{e}(j)$ and $\phi(i) \cancel{=} \phi_{e}(i)$
- MUST resolve potential resolution mismatches.


The depth frame has a resolution of $M\times N$.
The neuron tuning grid has a resolution of $A\times E \times K$
- If there is a difference in resolutions, many elements of the larger resolution entity may map to one of the elements in the lesser resolution entity.


