[[1,3 - Forward Pass]] $\leftarrow$ Back
[[1,5) NNs in Linear Algebra Form]] $\leftarrow$ Next

---
# Backward Passes & Weight Changing
Backward passes allow local errors, $\delta_j$, to be solved at each neuron.

CONCEPT OF LOCAL ERROR:
- Each local error of a neuron, j, contributes to the global error. Some neurons may contribute more to the global error than others.

$$
\delta = \vec{z} - \vec{y}
$$
- $\vec{z}$ is the EXPECTED, aka TARGET, output of the NN.
	- Only known during training.

- $\vec{y}$ is the ACTUAL, aka OBSERVED, output of the NN.
	- The output produced by the NN when it is given input values.

Backward passes originate at the output neurons, once a forward pass has been calculated, and then back propagates throughout the network, all the way to the neurons in the FIRST layer.
- Connections are changed, based on the value of the local error of a neuron, to minimise the local error in future forward passes.

$$
\delta_j = \sum_{i>j} \biggr[\delta_i c_{(j, i)}\biggr]
$$
![[Pasted image 20260131045008.png]]

Then, the strength of the connections where neuron j is the SINK are adjusted using the local error of neuron j.

$$
c'_{(p, j)} = c_{(p, j)}+\eta \delta_j \frac{df_j(e_j)}{de}f_p(e_p)
$$
- Do for ALL nodes part of a layer.

