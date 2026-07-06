[[1,3 - Geometric & Photometric Transformations]] $\leftarrow$ Back

---
# Non-invariance due to Scaling
Corner localisation, and many other things, can become non-invariant due to the scaling of an image.
- A detected feature which is detected as x may no longer be detected as x if it is scaled.

![[Pasted image 20260323121214.png]]

A detected corner, if rescaled, could no longer be detected as a corner. 

# Scale Invariant Detection
To allow a feature extractor/detector to be invariant to scale, 2 problems must be solved.
1) The size of filter to use on an image must be independently chosen based on properties of the image.
2) A characteristic scale of features in the image must be identified.

These 2 problems are solved by creating a function of a region of the image which is scale invariant.
- Scale invariant means it has the same shape even IF the image is resized.
- Then the local maximum of this function over the region is taken.

Optimal functions for scale detection have one sharp, stable maxima.
- A function which plateaus over a region is not optimal as it suggests multiple optimal scales are detected.
- A function with multiple maxima points is not optimal as it suggests multiple optimal scales are detected.

For usual images, an optimal function would be one which responds to contrast 
- Contrast: sharp local pixel intensity change.

These functions are called signature functions