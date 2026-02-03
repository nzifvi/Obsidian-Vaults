[[4,1 - Multilayer Feed-Forward Networks]] $\leftarrow$ Back

---
# Creating a Neural Network
To create a neural network, two approaches exist:
1) Define weights and biases, using tensors, yourself.
2) Use a predefined class provided by PyTorch.

# 1) Doing it Yourself
Must implement a process which achieves:
$$
\vec{y}=W\vec{x}+\vec{b}
$$

In implementation, an adaptation is made to the above formula due to reasons clarified below. The modified equation is:
$$
\vec{y}^T = \vec{x}^TW^T+\vec{b}^T
$$
- Row vectors used instead of column vectors: allows for entire rows of continuous memory to be read in all at once: LESS COMPUTATIONALLY EXPENSIVE.
- FLIP THE DIMENSIONS: rowNo is colNo, vice versa true.

```python
import torch

colNo1 = 2
rowNo1 = 4
rowNo2 = 1

W1Matrix = torch.rand([colNo1, rowNo1])
W2Matrix = torch.rand([rowNo1, rowNo2])

b1Vector = torch.rand([colNo1, 1])
b2Vector = torch.rand([rowNo1, 1])

def predict(x:torch.tensor):
	out1 = torch.tanh(torch.mm(x, W1Matrix)+b1Vector)
	out2 = torch.tanh(torch.mm(out1, W2Matrix)+b2Vector)
	return out2
	
inputData = torch.tensor([[0., 0.], [0., 1.], [1., 0.], [1., 1.]])
for i in range(inputData.size(0)):
	x = inputData[i].unsqueeze(0)
	print(predict(x))
```
```python
import torch

colNo1 = 2
rowNo1 = 4
rowNo2 = 1

weightsMatrixL1 = torch.rand([colNo1, rowNo1])
weightsMatrixL2 = torch.rand([rowNo1, rowNo2])

biasesVectorL1 = torch.rand([1, rowNo1])
biasesVectorL2 = torch.rand([1, rowNo2])

def predict(x, parameters):
	outputL1 = torch.tanh(torch.mm(x, weightsMatrixL1) + biasesVectorL1)
	outputL2 = torch.tanh(torch.mm(outputL1, weightsMatrixL2) + biasesVectorL2)
	return(outputL2)
	
print(predict([2, 2]))
```
# 2) Predefined PyTorch Class