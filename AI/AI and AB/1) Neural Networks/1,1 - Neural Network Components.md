[[1,2 - Transfer Functions]] $\leftarrow$ Next

---
# 1) Neurons
A neural network consists of neurons.

![[Pasted image 20260131043001.png]]

- $e_j$ is the ACTIVATION of neuron j: the weighted sum of it's inputs multiplied by the strength of connections coming into neuron j.
$$
e_j = \biggr(c_{(i,j)}f_{i}(e_i)+...+c_{(i+n, j)}f_{(i+n, j)}(e_{(i+n,j)})\biggr)+b_j
$$

- $b_j$ is the BIAS of neuron j.

- $c_{(i, j)}$ is the connection between neuron i and j.
	- Neuron is a source neuron, neuron j is a sink neuron.
	- The value, aka strength, of a connection is the result of the TRANSFER function of sink neuron in connection.

- $f_{j}(e_j)$ is the TRANSFER function of neuron j.
	- Applied to the result of the activation function.
	- Forwarded to neurons where neuron j is the SOURCE of the neuron.
	- $f_j(e_j)$ is the strength of the connections where neuron j is the source.


# 2) Layer
A neural network has multiple layers. Each layer has multiple neurons which are part of it.
![[Pasted image 20260131043430.png]]

For example, L1 has 3 neurons, L2 has 2 neurons, and L3 has 1 neuron: the output.
- Input is directly fed as into the first layer of NNs, input layers are just conceptual.