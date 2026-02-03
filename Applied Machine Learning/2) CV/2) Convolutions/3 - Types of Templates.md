[[2 - About Masks]] $\leftarrow$ Back
[[4 - Handling Boundaries]] $\leftarrow$ Next

---
# Types of Templates
Templates, produced by inverting the signs of the elements found in a mask, can be used to do very useful convolutions

The dimensions of the templates differ between types depending on what type of convolution is being performed.

# Horizontal Differencing
### Template
$$
T=[-1, +1]
$$
### Use
Replaces the element $A[i, j]$ with an approximation of the derivative in the image, along the x-axis, using finite differences.
- Slope of the chord

Used to measure the strength of vertical edges.

![[Pasted image 20260120175153.png]]

# Sobel Filter
### Template
$$
T = \begin{bmatrix}-1&0&1\\-2&0&2\\-1&0&1\end{bmatrix}
$$
### Use
Provides a way to reducing the noise in an image.

# Averaging Filter
### Template
$$
T_{rows\cdot cols}
$$
Let the number of elements, n, equal...
$$
n=rows \cdot cols
$$
Therefore...
$$
T=\begin{bmatrix}\frac{1}{n}&\frac{1}{n}&\frac{1}{n}\\\frac{1}{n}&\frac{1}{n}&\frac{1}{n}\\\frac{1}{n}&\frac{1}{n}&\frac{1}{n}\\\end{bmatrix}
$$
### Use
Smooths image noise by performing a weighted average in the neighbourhood defined by the mask.
![[Pasted image 20260120180104.png]]