[[1 - What is PyTorch]] $\leftarrow$ Back
[[3 - Dataset,  DataLoader]] $\leftarrow$ Next

---
# PyTorch layers
PyTorch layers are a set of classes which provide multiple types of neural networks layers used to build a neural network.
- Part of `torch.nn`

Most common ones are:
1) Linear layers: `torch.nn.Linear`
2) Convolutional layers: `torch.nn.Conv2d`
3) Recurrent layers: `torch.nn.RNN`, `torch.nn.LSTM`, `torch.nn.GRU`
4) Normalisation layers

# 1) `torch.nn.Linear`
`torch.nn.Linear` is used to define a simple linear layer in a neural network.
- performs a linear transformation on the incoming data: $\vec{x}$
$$
y=\vec{x}A^T+\vec{b}
$$

```python
class torch.nn.Linear(
	in_features,
	out_features,
	bias = True,
	device = None,
	dtype = None
)
```
Where...
- `in_features` denotes the number of input neurons in the layer.
- `out_features` denotes the number of output neurons in the layer.
- `dtype` denotes the datatype of the weights for the layer.
- `bias` denotes whether the layer has learnable, additive biases $\vec{b}$
	- default is `True`



# 2) `torch.nn.Conv2d`


```python
class torch.nn.Conv2d(
	in_channels,
	out_channels,
	kernel_size,
	stride       = 1,
	padding      = 0,
	dilation     = 1,
	groups       = 1,
	bias         = True,
	padding_mode = 'zeros',
	device       = None,
	dtype        = None
)
```
Where...
- `in_channels` determines the number of channels the input has.
- `out_channels` determines how many different kernels are applied to the input
	- Each output channel learns different features about the input (edges, textures, patterns)
- `kernel_size` determines the spatial dimensions of the kernel applied to do convolution.
	- can be int: creates a $n\times n$ kernel.
	- can be a tuple: creates a $n \times m$ kernel.
- `kernel_size` determines how many steps the kernel slides over the input.
	- can be int: determines the stride for both dimensions.
	- can be tuple: provides different strides in x and y.
	
# 3) Recurrent Layers

## 3.1) `torch.nn.RNN`

## 3.2) `torch.nn.LSTM`

## 3.3) `torch.nn.GRU`

# 4) Normalisation Layers