[[2 - Useful Attributes and Functions Members]] $\leftarrow$ Next

---
# About ndarray
An ndarray is a multidimensional array.
- Each element has a data type.

To declare a ndarray variable, use `numpy.array()` function member, passing a list, or another array, into it.
- Other ways exist to generate ndarrays.

```python
import numpy

array = numpy.array([1, 2, 3])
print(array)
```

# Accessing elements of ndarrays
Indexing an ndarray works like the following:
```python
array2 = numpy.array([[[1, 2], [2, 4]], [[4, 6], [6, 8]]])
print(array2)
```

$$
A[nIndex,...,rowIndex, colIndex]
$$
- nIndex is an ordinate from the highest dimension of the ndarray.
- rowIndex corresponds to a y ordinate in the y dimension.
- colIndex corresponds to an x  ordinate in the x dimension.

When loading images into an ndarray, the order is reversed.
- channelIndex is the lowest dimension.

Can use slicing on an ndarray to access ranges of elements.