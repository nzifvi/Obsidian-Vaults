[[1,4 - Backward Pass]] $\leftarrow$ Back
[[2,1 - Network Structures]] $\leftarrow$ Next

---
# NNs in Linear Algebra Form
The diagram representation of NNs are conceptual too. Neurons and layers are just linear algebra constructs and the processes of an NN, in linear algebra form, utilises linear algebra functions and operations.

## 1) Layers in Linear Algebra
In Linear Algebra form, a layer consists of...
1) A weights matrix.
2) An input vector received from the prior layer.
	- n rows (no. of neurons in the prior layer) and 1 col.
3) An output vector produced via the weights matrix and input vector.
	- n rows (no. of neurons in the current layer) and 1 col.
4) A biases column vector
	- n rows (no. of neurons in current layer) and 1 col.

Let...
- $W_i$ denote the weights matrix of $i^{th}$ layer.
- $\vec{x}$ denote the input column vector received by $i^{th}$ layer.
- $\vec{e}$ denote the output column vector produced by $i^{th}$ layer.

### Weights Matrix
The dimensions of a layer's weights matrix, $W$, is determined by...
1) The number of neurons in the current layer: determining the rows of the weights matrix.
2) The number of neurons in the previous layer: determining the columns of the weights matrix.

Let...
- x denote the number of neurons in the current layer.
- y denote the number of neurons in the prior layer.


The weights matrix is therefore defined as...
$$
W_{x \cdot y}=\begin{bmatrix}w_{(1,1)}&...&w_{(1,y)}\\w_{(2,1)}&...&...\\...&...&...\\w_{(x,1)}&...&w_{(x,y)}\end{bmatrix}
$$
- w$(i, j)$ is a weight $\in$ $W$ where i is the row index and j is the column index.
$$
\forall i,j. i,j \in\mathbb{N} | 1 \leq i \leq x \wedge 1 \leq j \leq y 
$$

### Neurons and Connections in Linear Algebra
Neurons, and also connections, are encoded in the weights matrix.

![[Pasted image 20260131051456.png]]
Each row of the weights matrix = a neuron in the layer.

...and...

![[Pasted image 20260131051545.png]]
Each element, part of a row, represents a source neuron connecting to the neuron the row represents.
- Columns represent source neurons.

The weights part of the weights matrix are the strength of the connections in a neural network.

The indices (i, j) represent (sink, source).
- This is how the connections are encoded.

## 2) Forward Passes in NN Linear Algebra Form
$$
\vec{a_i}= f_i\biggr(W_i\vec{x_i} + \vec{b_i}\biggr)
$$
- $\vec{x_i} = \vec{a_{(i-1)}}$ - input vector of current layer is output vector of the prior layer.

## 3) Backward Passes in NN Linear Algebra Form
### Calculating Local Error
$$
\delta_j = \biggr(W_j^T\delta_{(j+1)}\biggr) \odot \frac{df(\vec{e_i})}{de}
$$
#### Why Transpose Weights Matrix?
![[Pasted image 20260131053238.png]]

$$
L2.W_{2\cdot3}=\begin{bmatrix}w_{(1,1)}&w_{(1,2)}\\w_{(2,1)}&w_{(2,2)}\\w_{(3,1)}&w_{(3,2)}\end{bmatrix}
$$
Transposing the weights matrix results in...
$$
L2.W_{2\cdot3}^T = \begin{bmatrix}w_{(1,1)}&w_{(1,2)}&w_{(1,3)}\\w_{(2,1)}&w_{(2,2)}&w_{(2,3)}\end{bmatrix}
$$
which can be interpreted as REVERSING the directions of the connections of a NN: accessing outgoing connections from the current layer.
![[Pasted image 20260131053648.png]]

### Calculating Weight Gradient
$\nabla W$ is the weight gradient of a layer.
- Let i denote the $i^{th}$ layer.
$$
\nabla W_j = \delta_j\vec{a_{(j-1)}}^T
$$

#### Why Transpose the Prior Layer's Output Vector
Same reason as the weights matrix is transposed.

### Updating Weights of Layer
$$
W_j' = W_j - \eta \nabla W_j
$$