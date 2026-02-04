
---
# Requirements to Implement an NN
1) predict function
	- Used to predict an output based on input. Essentially runs the ENTIRE NN.
2) training loop
	- Used to update the weights, and biases, of the NN.

# 1) Predict Function
Predict function used to run the entire NN.
- Different ways exist to implement it.
- For a simple NN with only a few layers, can be done without any loops.

```python
import torch

W1 = torch.rand([2, 4], requires_grad = True)
b1 = torch.rand([1, 4])

W2 = torch.rand([4, 1], requires_grad = True)
b2 = torch.rand([1, 1])

def predict(x, W1, W2, b1, b2):
	out1 = torch.relu(torch.mm(x, W1) + b1)
	out2 = torch.relu(torch.mm(out1, W2) + b1)
	return out2
```

Each statement, besides the return, implements the below mathematical function.
$$
\vec{out_1} = g\biggr(\vec{x}^TW^T\ + \vec{b}^T \biggr)
$$
- Multiplies matrices together and then adds the biases.
- Applies transfer function to result.

# Training Loop
Training loop uses:
- loss function (part of torch.nn library).
- optimiser (part of torch.optim library).

Function members of both these objects are used during the training loop process to perform back propagation and update the weights based on that.

```python
import torch.nn as nn
import torch.optim as optim

lossFunction = nn.MSELoss() #define loss function
optimiser = optim.SGD([W1, W2, b1, b2], lr=0.01) #define optimiser

for epoch in range(epochAmount):
	x = inputData[i].unsqueeze(0)
	y = outputData[i].unsqueeze(0)
	
	optimiser.zero_grad() # clear past gradients
	estimatedOuput = predict(x, W1, W2, b1, b2)
	loss = lossFunction(estimatedOutput, y)
	lossFunction.backward() # calculate gradients of loss function.
	optimiser.step() # update weights in weight matrices.
	
	
```