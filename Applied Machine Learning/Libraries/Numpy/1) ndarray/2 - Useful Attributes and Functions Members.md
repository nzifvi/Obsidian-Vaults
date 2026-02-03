[[1 - What is ndarray]] $\leftarrow$ Back

---
# Useful Attributes
## shape
Returns a tuple which tells how many elements exist per dimension of a ndarray.

## ndim
Returns the number of dimensions which exist in an ndarray.

# Useful Function Members
## Geometric Transformations

#### reshape()
Alters dimensions of an ndarray without losing/altering data.

Requires a tuple as the input:
- With a 1D array of n elements, can reshape the array into any combination that multiplies to n.
- e.g: let n = 12, can reshape 1d array into (3, 4), (2, 2, 3), (1, 2, 2, 3), etc...

#### transpose() / .T
Transposes the ndarray.

If wanting to control which axes get swapped, label the desired order of the axes.
- IF TRANSPOSING IMAGE, DO NOT SWAP CHANNEL: ONLY SWAP ROW AND COL.
#### flatten()
Turns a multidimensional array into a 1d array, keeping all elements.

## Statistical Analysis

#### mean()
Returns mean along an axis, or mean of all elements.
- If no parameter provided, returns mean of all elements.
- If an axis is provided, i.e. which dimension to get the mean of, returns the mean along that dimension.

#### sum()
Returns sum along an axis, or sum of all elements.
- If no parameter provided, returns sum of all elements.
- If an axis is provided, i.e. which dimension to get the mean of, returns the sum along that dimension.

#### max()/min()

#### argmax()

# Cleanup/Logic

#### astype()
Converts datatypes of elements, type given as parameter on function member call.
- Can be applied to slice of ndarray or a singular element of the ndarray.
- If performed without any parameters, ALL elements will have their type converted.
#### clip()
Forces ALL values to stay within a range, given as a min and max parameter.
- If a value < min, the value will be set to min.
- If a value > max, value will be set to max.

#### copy()
Used to create a deep copy of an ndarray, useful for performing operations such as swapping subarrays around within an ndarray.
- Without copy, a reference is assigned to a variable. Any changes made to the reference will be also made to the original.