[[3 - Uses for RNNs]] $\leftarrow$ Back

---
# How to Train RNNs
Training RNNs involves backpropagating through time rather than layers.
- Very difficult process.

Recall...
$$
\vec{y}(t+1) = g\biggr(W\vec{y}(t) + \vec{I}+\vec{\theta}\biggr) 
$$
![[Pasted image 20260205105142.png]]

To train an RNN via backprop, backpropagation is performed at each time step that the RNN was ran at, rather than at each layer.
- Concept of layers cannot work with RNNs, as they are bi-directional.


Method only works for small RNNs.
- Method ALSO has a lot of problems: vanishing and/or exploding gradients.

## Components of Training RNNs
### 1) Loss Function
Loss functions for RNNs are slightly more complex than basic multilayer feed-forward NNs.
- Have to account for time.

Done by defining a loss function, $\mathcal{L(Y, \hat{Y})}$ over time:
- $\mathcal{Y}$ denotes set of estimated outputs, produced by RNN.
- $\mathcal{\hat{Y}}$ denotes set of actual outputs, produced by RNN.
- Sets have pairs of elements at equivalent points in time.
$$
|\mathcal{Y}| = |\mathcal{\hat{Y}}|=T
$$
- T is the total number of iterations, aka time steps, done in a simulation of RNN.

$$
\mathcal{L(Y, \hat{Y})}=\sum_{t=1}^{T}\biggr[\mathcal{l}(\vec{y}(t), \hat{y}(t))\biggr]
$$
$$
\mathcal{l}(\vec{y}(t), \hat{y}(t))= ||\vec{y}-\hat{y}||^2
$$
1) Take difference between vectors.
2) Take magnitude of difference between vectors.
3) Square the magnitude.
4) Result is the loss.
# How to Remove Problems in Training
Methods exist to remove problems during training of an RNN:
- Attractor Neural Network (ANNs)
	[[4,2 - Attractor Neural Network]]	
- Echo State Machines (ESMs).
	[[4,3 - Echo State Machines]]

# Example of Updating Weights in RNN
