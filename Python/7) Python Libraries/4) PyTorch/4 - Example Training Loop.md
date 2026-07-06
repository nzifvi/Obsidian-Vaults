[[3 - Dataset,  DataLoader]] $\leftarrow$ Back

---

```python
import torch.nn as nn
from torch.utils.data import DataLoader
from torchvision import datasets, transforms

# suppose a neural network object called model exists.

trainLoader = datasets.MNIST(
	root = "...", # suppose
	train = True,
	download = True,
	transform = transform
)

epochAmount = 100
for epoch in range(0, epochAmount):
	model.train()
	# iterate over the dataLoader EACH epoch
	for x, yActual in trainLoader:
		yPredicted = model(x)
```