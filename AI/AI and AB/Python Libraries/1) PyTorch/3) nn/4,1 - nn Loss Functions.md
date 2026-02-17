[[3 - nn Transfer Functions]] $\leftarrow$ Back

---
# nn Loss Functions
nn module provides multiple loss functions which can then be used to calculate loss during back propagation of a neural network.

## Defining Loss Functions

```python
import torch
import torch.nn as nn

lossFunc1 = nn.MSELoss()
lossFunc2 = nn.CrossEntropyLoss()
```

NOTE: more types of loss functions do exist.
# Calling Loss Functions
To call a loss function, you must provide:
- predicted outputs.
- target outputs.
of training data

```python
predictedOutputs = []
targetOutputs = []
loss = lossFunc1(predictedOutputs, targetOutputs)
```

NOTE: can just pass singular scalar values of a predicted output and target output to calculate the loss.