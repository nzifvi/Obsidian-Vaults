[[1 - What is optim]] $\leftarrow$ Back

---
# Optimising Weights and Biases via Optim
During training, to optimise the weights post gradient calculation, use the function member of an optimisation algorithm `step()`.
- `step()` updates the values of the weights and biases, in memory, passed as parameters during object initialisation

```python
import torch
import torch.nn as nn
import torch.optim as optim

l1 = Linear(4, 12)
l2 = Linear(12, 1)

lossFunction = nn.MSELoss()

paramList = list(l1.parameters()) + list(l2.parameters())
optimiser = optim.SGD(paramList, lr = 0.001)


optimiser.zero_grad()

# suppose prediction completed by NN...
predictedOutput = 1.3
targetOutput = 4.1

loss = lossFunction(predictedOutput, targetOutput)

loss.backward()

optimiser.step()
```

MUST be done exactly in above order...
- `zero_grad()` used to clear the gradients of the optimiser object from past optimisations.
	- MUST be done otherwise past gradients still present for current calculations.

- `loss.backward()`, where loss is the return from a loss function, used to calculate gradients

`optimiser.step()`, the function member of initialised Optimiser object, used to update the weights matrices and bias vectors passed during initialisation.


