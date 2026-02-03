[[2,1 - Network Structures]] $\leftarrow$ Back

---
# What is a Hopfield Network?
Hopfield network is a recurrent neural network which...
- Has connections between nodes which are bidirectional.
- All weights are symmetric:
$$
W(i, j)=W(j, i)
$$
- All nodes are BOTH input and output nodes.
- Sign function is used as the activation function.

![[Pasted image 20260128182030.png]]

# Uses of Hopfield Networks
Hopfield networks function as associative memory.
- After training on examples, new stimulus causes network to have an activation pattern which corresponds to a member of the training set which best matches the new stimulus.