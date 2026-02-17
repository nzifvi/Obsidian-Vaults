[[2 - Optimising Weights and Biases via Optim]] $\leftarrow$ Next

---
# What is optim?
optim is a pytorch module used to provide optimisation algorithms used to train a neural network.
- Changes elements of BOTH weights matrices and bias vectors.

Multiple types of optimisation algorithms exist.
- All implement variants of gradient descent. Normally variants of adaptive gradient descent.
- Some are...
1) SGD
2) Adam
3) RMSProp
4) Adagrad
5) Adadelta
6) AdamW

# Defining the Optimiser
To define the optimiser...
```python
import torch
import torch.nn
import torch.optim

l1 = nn.Linear(10, 32)
l2 = nn.Linear(32, 4)
l3 = nn.Linear(4, 1)

paramList = list(l1.parameters()) + list(l2.parameters()) + list(l3.parameters())
optimiser = optim.SGD(paramList, lr=0.001)
```
- Takes tensors as an input parameter.
- Takes a float value, lr (learning rate), also as an input parameter.