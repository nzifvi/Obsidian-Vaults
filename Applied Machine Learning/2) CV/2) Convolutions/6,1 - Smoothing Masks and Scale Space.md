[[5 - scipy convolve2d]] $\leftarrow$ Back
[[6,2 - Gaussian Mask]] $\leftarrow$ Next

---
# 1) What are Smoothing Masks?
Smoothing masks, such as the averaging filter, "smooth" the image by reducing noise via some mechanism.

Fundamentally, the weights of ANY smoothing mask should add up to 1.
- This preserves grey-levels, or the intensity levels of a given channel.
- Can be done for ANY mask with positive weights via normalisation...
	1) Calculate sum of weights.
	2) Divide each weight by the sum of weights.

Multiple smoothing masks exist:
- Most simple is the averaging filter ([[3 - Types of Templates]])
- Another is the Gaussian smoothing mask [[6,2 - Gaussian Mask]].

# 2) Scale Space
Images are sometimes considered as structures in a scape space.

A property of an image, such as grey-level, is considered to be a function of BOTH...
1) position (i, j).
2) scale $\sigma$

Scale can be regarded as being set by the parameter of a smoothing mask.
