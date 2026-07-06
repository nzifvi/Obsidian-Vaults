[[2,1 - Introducing Neurons]] $\leftarrow$ Back
[[3 - Recording Neuronal Responses]] $\leftarrow$ Next 

---
# 1) Modelling Synaptic Weights
The synaptic connection between a pre-synaptic neuron $j$ and post-synaptic neuron $i$ has a weight
![[Pasted image 20260622113622.png]]
- The synaptic weight between pre-synaptic neuron j and post-synaptic neuron i is $w_{i,j}(t)$

There can be N pre-synaptic neurons
$$
N=\{1,...,n\}
$$![[Pasted image 20260622113900.png]]
This forms a synaptic weight vector for EACH post-synaptic neuron
- 1 element per pre-synaptic neuron
- Post-synaptic neuron i's weight vector is equal to...
$$
\vec{w}_i(t) = \begin{bmatrix}
w_{i,1}(t)\\
...\\
w_{i,j}(t)\\
...\\
w_{i,n}(t)
\end{bmatrix}^T
$$
There can also be M post-synaptic neurons
$$
M=\{1,...,m\}
$$
$$
W=\begin{bmatrix}
\vec{w}_1(t)\\
...\\
\vec{w}_i(t)\\
...\\
\vec{w}_m(t)
\end{bmatrix}
$$