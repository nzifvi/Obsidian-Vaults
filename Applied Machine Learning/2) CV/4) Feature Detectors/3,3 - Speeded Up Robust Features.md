 [[3,2 - Scale Invariant Feature Transform]] $\leftarrow$ Back
[[3,4 - Binary Robust Independent Elementary Features]] $\leftarrow$ Next

---
# What is Speeded Up Robust Features
Speeded Up Robust Features, SURF, is a faster version of SIFT. SURF achieves this with...
1) Box filter approximations.
	- SIFT uses Gaussian filters to smooth the image: computationally expensive.
	- SURF approximates the Gaussian filters with box filters: simple rectangular filters with uniform weights.
	- Box filters = cheaper to compute as they only involve additions instead of multiplications.
2) Integral images.
	- SURF uses integral images to make box filters even faster
$$
S_{x,y}=\sum_{i=0}^{x}\sum_{j=0}^{y}\biggr[I_{i,j}\biggr]
$$
- $S_{x,y}$ stores the sum of all pixel values in a box filter.
- Once the integral image is computed, the sum of any rectangular region in the image can be calculated with 4 corner points: regardless of box size.
- Makes integral images an O(1) operation per box filter operation.

