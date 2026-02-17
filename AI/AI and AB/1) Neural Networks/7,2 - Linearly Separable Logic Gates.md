[[7,1 - Logic Gates as NNs]] $\leftarrow$ Back

---
# NN Structure for Linearly Separable Logic Gates
Input vector for nn logic gate...
- Has n inputs.
$$
\vec{x}=\begin{bmatrix}
x_1\\...\\x_n
\end{bmatrix}
$$
Weights matrix for nn logic gate...
- Has n inputs, 1 output...

$$
W_{1\cdot n}
$$

Bias vector for nn logic gate...
- Has 1 output...
$$
\vec{b} = \begin{bmatrix}b_1\end{bmatrix}
$$

A forward pass is equal to...
$$
y= g\biggr(W^T\vec{x}+\vec{b}\biggr)
$$
- For linearly separable logic gates, use step function as transfer function.

This way, a boolean function f, is equal to...
$$
f(x_1,...,x_n)=step\biggr(W^T\vec{x}+\vec{b}\biggr)
$$

By looking at a logic gate's truth table, you can implement it
# AND Gate

| $x_1$ | $x_2$ | AND OUTPUT |
| ----- | ----- | ---------- |
| 0     | 0     | 0          |
| 0     | 1     | 0          |
| 1     | 1     | 1          |
| 1     | 0     | 0          |

$$
W_{2\cdot1}=\begin{bmatrix}1\\1\end{bmatrix}
$$
- 2 input neurons, 1 output neuron (output of gate)
$$
\vec{b_{1\cdot1}}=-1.5
$$
$$
\vec{e}=W\vec{x}+\vec{b}=\begin{bmatrix}1\\1\end{bmatrix}\begin{bmatrix}x_1\\x_2\end{bmatrix}-1.5
$$
Output, $g(\vec{e})$ is only 1 when BOTH inputs, $x_1, x_2$, are GREATER than 0.
# OR Gate
| $x_1$ | $x_2$ | AND OUTPUT |
| ----- | ----- | ---------- |
| 0     | 0     | 0          |
| 0     | 1     | 1          |
| 1     | 1     | 1          |
| 1     | 0     | 1          |
$$
W_{2\cdot1}=\begin{bmatrix}1\\1\end{bmatrix}
$$
- 2 input neurons, 1 output neuron (output of gate)
$$
\vec{b_{1\cdot1}}=-0.5
$$
$$
\vec{e}=W\vec{x}+\vec{b}=\begin{bmatrix}1\\1\end{bmatrix}\begin{bmatrix}x_1\\x_2\end{bmatrix}-0.5
$$
Output, $g(\vec{e})$ is only 1 when one of or both of inputs, $x_1, x_2$, are GREATER than 0.
# NAND Gate

# NOR Gate

# NOT Gate