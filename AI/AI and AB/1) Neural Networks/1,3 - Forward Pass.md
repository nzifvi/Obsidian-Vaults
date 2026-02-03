[[1,2 - Transfer Functions]] $\leftarrow$ Back
[[1,4 - Backward Pass]] $\leftarrow$ Next

---
# Forward Passes
A forward pass of a neural network is the act of the NN producing an output, given input values, by linearly propagating values from L1 to the output layer.

- Done by sequentially passing transfer functions along the connections between neurons, all the way to the neurons in the output layer.

- Output of the output layer's neurons is the FINAL output of NN.

![[Pasted image 20260131043942.png]]

Considering node j...
- Let $y_j = f_j(e_j)$
- $i$ is the starting index of the connections where node j is the sink.
$$
e_j = \sum_{x=1}^{n}\biggr[c_{(i+x, j)f_{(i+x)}}(e_{(i+x)})\biggr]
$$