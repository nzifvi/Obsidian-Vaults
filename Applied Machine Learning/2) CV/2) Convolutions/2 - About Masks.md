[[1,1 - About Convolutions]] $\leftarrow$ Back
[[3 - Types of Templates]] $\leftarrow$ Next

---
# About Masks
Masks define the number of elements which will be captured per convolution.
$$
Mask_{Rows\cdot Cols}
$$
- $Rows\cdot Cols$ elements will be captured PER convolution.

Masks can be vectors or matrices.

Masks have a coordinate which represents the current indices the mask starts on.
- Used to define a submatrix, of the matrix representing an image, that the convolution is currently happening to.

![[Pasted image 20260120173102.png]]

Therefore the template of a mask is applied to a submatrix defined by...
$$
A[rowIndex+rows, colIndex+cols]
$$

Per convolution, the col index is incremented by 1 UNTIL $colIndex ==$ no. of cols in matrix.
- When all columns in the current row of the matrix are processed, colIndex is reset to 0 and rowIndex is incremented by 1.
- Terminates when $rowIndex= no. of rows in matrix \wedge colIndex = cols$ (ALL CONVOLUTIONS APPLIED BY TEMPLATE)

$$
Mask_{M\cdot N}
$$

$$
A[i, j]_{convoluted}=\sum_{m=0}^{M-1}\sum_{n=0}^{N-1}\biggr[A[i+m, j+n]\cdot Mask[m, n]\biggr]
$$

- convolution is a weighted sum of the local neighbourhood, defined by the mask.
- (m, n) is referred to as the origin of the mask.

# Properties of Masks
### 1) INCREASING/DECREASING DIMENSIONS OF MASK
If you increase/decrease the dimensions of the mask, template's dimensions are increased/decreased by an equivalent amount.

Has the consequence of including/excluding more elements in the neighbourhood defined by the mask.

### 2) TRANSPOSING MASK APPLIES MASK IN OPPOSITE DIMENSION
If you transpose a mask which acts on the x axis, it's transposition will act on the y axis.
