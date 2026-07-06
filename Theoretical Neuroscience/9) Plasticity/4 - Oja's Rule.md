
---
# 1) What is Oja's Rule?
Oja's rule is an implementation of LTP which provides stable Hebbian weight change.
- Pure Hebbian learning has no upper bound: it can grow unbounded if firing is correlated.
- Does not directly implement LTD dynamics.

$$
w_{i,j}(t+1) = w_{i, j}(t)+\eta(r_i\cdot r_j)
$$

Fix: normalise each weight part of a weight vector

$$
\vec{w_i}(t)=\begin{bmatrix}
w_{i, 1}(t)\\
...\\
w_{i, n}(t)
\end{bmatrix}
$$
$$
\hat{w}_{i,j}(t) = \frac{w_{i,j}(t)+\eta(r_i\cdot r_j)}{||\vec{w_i}(t) + \eta(r_i\cdot\vec{r})||}
$$
- Where $\vec{r}$ is the firing rate of all pre-synaptic neurons which connect to $i^{th}$
