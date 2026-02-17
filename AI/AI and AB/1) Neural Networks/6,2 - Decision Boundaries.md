[[6,1 - Hyperplanes]] $\leftarrow$ Back

---
# What are Decision Boundaries?
Decision boundaries define an $n^{th}$ dimensional hyperplane for a neuron where the model's output switches from one class to another.

$i^{th}$ neuron's decision boundary is defined as...
$$
\vec{w_i}\vec{x}+b_i
=0$$
- A neuron's forward pass WITHOUT transfer function applied set to equal 0.


$$
W=\begin{bmatrix}w_{1,1}&w_{1,2}\\w_{2,1}&w_{2,2}\end{bmatrix}, \vec{b}=\begin{bmatrix}b_1\\b_2\end{bmatrix}
$$
$$
\vec{w_1}=\begin{bmatrix}w_{1,1}&w_{1,2}\end{bmatrix}, \vec{w_2}=\begin{bmatrix}w_{2,1}&w_{2,2}\end{bmatrix}
$$
Since there are 2 neurons, 2 hyperplanes exist:
$$
y_1=g\biggr(\vec{w_1}\vec{x}+b_1\biggr)
$$
$$
y_2=g\biggr(\vec{w_2}\vec{x} + b_2\biggr)
$$

$$
\vec{w_1}\vec{x}+b_1
=0 \Rightarrow
\begin{bmatrix}
w_{1,1}&w_{1,2}
\end{bmatrix}
\begin{bmatrix}
x_1\\x_2
\end{bmatrix}
+b_1
=(w_{1,1}x_1+w_{1,2}x_2)+b_1
$$
Solving neuron 1's decision boundary...
$$
(w_{1,1}x_1+w_{1,2}x_2)+b_1=0
$$

Decision boundary partitions space into 2 subspaces.

![[Pasted image 20260212094209.png]]

Can figure out if an output is part of either subspace based on inequalities...
- If...
$$
(w_{1,1}x_1+w_{1,2}x_2)+b_1 < 0 
$$
- ... then inputs are part of $C_1$ subspace.

- If...
$$
(w_{1,1}x_1+w_{1,2}x_2)+b_1 \geq 0
$$
- ... then inputs are part of $C_2$ subspace.