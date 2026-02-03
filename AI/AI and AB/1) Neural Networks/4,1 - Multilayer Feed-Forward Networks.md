[[3 - Perceptrons]] $\leftarrow$ Back
[[5 - Implementing NN in Python]] $\leftarrow$ Next

---
# What are Multilayer Feed-Forward Networks?
A multilayer feed-forward network is one where there are one or more hidden layers between the input and output layer.
![[Pasted image 20260128191857.png]]

# Learning for Multilayer Feed-Forward Networks
Example inputs fed to the neural network.
- If the output vector matches the target, nothing is done.
- If there is an error (difference between output and target vector), weights are adjusted throughout the network to reduce the error.
	- Done by assessing blame for the error and divide it among weights which contribute towards the error.

In multilayer networks, there are many weights connecting the input and output layer.
- Each of these weights contribute to more than one output node.
- Back-propagation algorithm used to divide the contribution of each weight to an error.
$$
Err_i = \vec{t_i}-\vec{o_i}
$$
## Updating Weights between Hidden Layer and Output Layer
At the output layer of a multilayer feed-forward network, there are differences when compared to perceptrons:
- Activation value of a hidden node, part of the prior hidden layer, will be used as opposed to an activation value from an input node.

The weight update rule for a weight $W_{(j, i)}$ is equal to...
$$
W_{(j, i)} \leftarrow W_{(j,i)}+\alpha \cdot a_j \cdot\Delta_i
$$
- $\Delta _i = Err_i \frac{dg(in_i)}{dx}$ 
## Updating Weights between Input Layer and Hidden Layer
Error back-propagation is used to update weights between input layer and hidden layer.
- Done to calculate an equivalent metric of the error calculated for the output layer.

Idea of back-propagation:
- Hidden node j is responsible for a fraction of the error in $\Delta _i$ in EACH of the output nodes.
$$
\Delta_{j}=\frac{dg(in_j)}{dx} \sum_i \biggr[W_{(j, i)} \Delta_i\biggr]
$$
The weight update rule between an input and hidden layer is almost identical to the weight update rule between hidden layer and output layer:
- k is a node in the input layer.
- j is a node in the hidden layer which comes immediately after the input layer.
$$
W_{(k, j)} \leftarrow W_{(k, j)} + Q \cdot I_{k}\cdot \Delta_j
$$