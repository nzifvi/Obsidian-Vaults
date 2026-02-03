
---
# What are PyTorch Tensors?
In PyTorch, a tensor is a multi-dimensional data structure used to contain values.
- Vectors (1D arrays)are 1D tensors.
- Matrices (2D arrays) are 2D tensors.
- Cubes (3D arrays) are 3D tensors

A general rule of thumb is that an $n^{th}$ dimension array is an $n^{th}$ rank tensor.

PyTorch tensors are similar to numpy ndarrays, however, one big distinction exists.
- PyTorch tensors can run on either CPU or GPU (highly efficient for parallel computations, like the ones used in neural networks).

# How to Create a Tensor Object
```python
import torch # PyTorch library

dataVector = [1, 2, 3] #1D vector
dataTensor = torch.tensor(dataVector) # call initialiser for Tensor object
print(dataTensor)
```

Other ways exist to initialise a Tensor object...
## 1) With Random Values
Done using torch's `randn` function member:
```python
newTensor = torch.randn((2, 2)) # 2 rows, 2 columns (2d tensor)
print(newTensor)
```
## 2) Zero Tensor
Creates a tensor where all elements are initialised to zero, using torch's `zeros` function member:
```python
zerosTensor = torch.zeros([2,2], dtype=torch.int32)
print(zerosTensor)
```

## 3) Ones Tensor
Creates a tensor where all elements are initialised to 1, using torch's `ones` function member:
```python
onesTensor = torch.ones([2,2], dtype=torch.int32)
```
## 4) 
# Tensor Attributes
A Tensor object has 3 public attributes:
1) shape
	- denotes the dimensions of the Tensor
2) dtype
	- denotes the datatype of the Tensor's elements.
3) device
	- denotes on which processing unit the Tensor is stored.