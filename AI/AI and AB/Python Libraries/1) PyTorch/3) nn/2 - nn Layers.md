[[1 - What is nn]] $\leftarrow$ Back
[[3 - nn Transfer Functions]] $\leftarrow$ Next

---
## nn Layers
torch.nn provides an object, `Linear` which models a layer in an NN.

`Linear`'s constructor requires 2 parameters:
1) inFeatures (number of neurons from prior layer or number of inputs)
2) outFeatures (number of neurons in current layer)

```python
import torch
import torch.nn as nn

nn.Linear(56, 128)
nn.Linear(128, 12)
nn.Linear(12, 1)
```
