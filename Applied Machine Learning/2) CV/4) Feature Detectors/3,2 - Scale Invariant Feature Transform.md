[[3,1 - Feature Descriptors]] $\leftarrow$ Back
[[3,3 - Speeded Up Robust Features]] $\leftarrow$ Next

---
# What is the Scale Invariant Feature Transform?
Scale Invariant Feature Transform, SIFT, is a way of computing gradient orientation for each pixel in a given filter.
- Creates a histogram over edge orientations weighted by magnitude.

Idea is to...
1) Take a 16x16 window about a detected feature.
	- Feature is at centre of window
	![[Pasted image 20260323194450.png]]

2) Compute gradient orientation for each pixel caught within the window.
	- Done using a Sobel filter which is convoluted with the window
	- Let $G_x$ denote the horizontal gradients
	- Let $G_y$ denote the vertical gradients

$$
G_x = Convolute(I, K_x)
$$
$$
G_y
=Convolute(I, K_x^T)$$
- The magnitude of the gradients can be calculated with...

$$
|G| = \sqrt{G_x^2+G_y^2}
$$
- The gradient orientations can be calculated with...
$$
\theta = arctan\biggr(\frac{G_y}{G_x}\biggr)
$$
3) Create histogram over edge orientations weighted by magnitude.
	- Divide the range of $[0, 2\pi]$ into n bins. $\frac{2\pi}{n}$ denotes how many radians each bin covers.
	- For all pixels, figure out what bin it falls into based on the corresponding gradient orientation.
	- Add the gradient magnitude to the corresponding bin (weighting step).

$$
Bin_n = [l_1, u_1]
$$
$$
\theta_{i,j} \in [l_1, u_1] \Rightarrow Value(Bin_n)' = Value(Bin_n) + |G_{i,j}| 
$$
