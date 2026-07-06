[[4 - Canny Edge Detector]] $\leftarrow$ Back

---
# What is a Laplacian Template?
Second order derivatives can be approximated using the below convolutional template
$$
T_{1\times3}=\begin{bmatrix}-1&2&-1\end{bmatrix}
$$
$$
\mathcal{L}_{3\times3}=T^T \odot T
$$
$$
\begin{bmatrix}-1\\2\\1\end{bmatrix} \odot \begin{bmatrix}-1&2&-1\end{bmatrix} = \begin{bmatrix}0&-1&0\\-1&4&-1\\0&-1&0\end{bmatrix}
$$
So...
$$
\mathcal{L}_{3\times3}=\begin{bmatrix}0&-1&0\\-1&4&-1\\0&-1&0\end{bmatrix}
$$
$\mathcal{L}_{3\times3}$ is know as the Laplacian template.