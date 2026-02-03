[[1,5) NNs in Linear Algebra Form]] $\leftarrow$ Back
[[3 - Perceptrons]] $\leftarrow$ Next

---
# 1) Network Structures
Many types of neural network structures exist.
- Each results in different computational properties.
- Main distinction of neural network structure is feed-forward and recurrent networks.

## 1.2) Feed-Forward Structure
In feed-forward network, links between nodes are unidirectional.
- No cycles exist.

Feed-forward networks are DAGs.

No cycles allows for computation to proceed linearly from input nodes to output nodes.
- Activation function relies on nothing but the current weights.
- No activation is "fed back" due to the fact that links are unidirectional.

## 1.3) Recurrent Structure
Links between nodes can form arbitrary topologies. 

Human brain is a recurrent network.
- Activation is fed back to nodes which caused the activation.

Recurrent networks have internal states stored in the activation level of the units.
- Computation is much less orderly compared to feed-forward networks.

Recurrent networks can...
- Become unstable
- Oscillate
- Exhibit chaotic behaviour.

Given inputs, it can take a while to compute stable outputs.
- Also more difficult for recurrent networks to learn.

Due to increased complexity, recurrent networks can implement more complex agents and model more complex systems.

Types of Recurrent Networks
- [[2,2 - Hopfield Networks]]
# 2) Layers
A neural network can be separated into separate layers. Each layer consists of a set of nodes which belong to that layer.
![[Pasted image 20260128180727.png]]

In a layered feed-forward network structures, nodes in current layer ONLY connect to nodes in the next layer.

## 2.1) Types of Layers
There are 3 types of layers. Each node has the same type as it's layer.
1) Input Layer
2) Hidden Layer
3) Output Layer

A node part of the input layer is an input node.

![[Pasted image 20260128182938.png]]

- $I_j$ denotes that node $j$ is an input node: part of the input layer.
- $H_j$ denotes that node j is a hidden node: part of a hidden layer.
- $O_j$ denotes that node j is an output node: part of output layer.

### Input Units & Layers
Input units are nodes part of the input layer.
- Activation values of input units are determined by environment.
- Denoted as $I$

### Hidden Units & Layers
Hidden units are nodes part of the hidden layer.
- Cannot be directly observed by noting input and output behaviour of neural network.
- Denoted as $H$

Networks with one or more hidden layers are called multilayer networks.

Networks with no hidden layers are called perceptrons.
### Output Units & Layers
Output units are nodes part of the output layer.
- Denoted as $O$

# 3) Optimal Network Structure
Choosing optimal network structure is vital when creating a neural network.
- If a network is too small, it may be incapable of representing a desired function.
- If network is too big, it will be able to memorise the training data and not handle unseen inputs well.

An overfitted neural network means that there are too many parameters, such as weights, in the model.

## Ways to Achieve Optimal Network Structure
1) Genetic Algorithms
	- Selects best current model from a generation and then creates future models from best current model.
2) Hill-climbing Searches
	- Selectively modifies an existing neural network's structure.
		- Starts with a big structure and reduces it.
		OR
		- Starts with a small structure and increases it.
3) Optimal Brain Damage
	- Network is initially trained and an algorithm identifies an optimal set of connections which can be dropped (weights set to 0).
	- Network is then retrained and checked to see if performing better/worse.
	- Process is repeated