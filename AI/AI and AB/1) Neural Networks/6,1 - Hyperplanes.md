[[6,2 - Decision Boundaries]] $\leftarrow$ Next

---
Recall... in a weights matrix W...
$$
W=
\begin{bmatrix}
w_{1,1}&...&w_{1,n}\\
...\\
w_{n,1}&...&w_{n,n}
\end{bmatrix}
$$
- EACH row corresponds to ONE NEURON.

Each neuron has it's own hyperplane in input space of $\vec{x}$ 

The $i^{th}$ neuron is equal to...
$$
\vec{w_i}=\begin{bmatrix}w_{i,1}\\...\\w_{i,n}\end{bmatrix}
$$


Each neuron has it's own hyperplane in input space of $\vec{x}$ 
- A hyperplane is an $n^{th}$ dimensional plane which divides space into two parts.
- Hyperplane for neural networks classifies 2 types of inputs, based on what side of the plane they exist on.
- Hyperplanes ARE decision boundaries.

$$
W=\begin{bmatrix}1&1\\-1&1\end{bmatrix}, \vec{b}=\begin{bmatrix}-1.5\\0.5\end{bmatrix}
$$
$$
\vec{w_1}=\begin{bmatrix}1\\1\end{bmatrix}, \vec{w_2}=\begin{bmatrix}-1\\1\end{bmatrix}
$$
Since there are 2 neurons, 2 hyperplanes exist: