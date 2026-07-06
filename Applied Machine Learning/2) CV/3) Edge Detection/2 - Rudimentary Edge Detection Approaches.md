[[1 - Edge Detection as a Problem]] $\leftarrow$ Back
[[3 - Edge Detection and Spatial Scale]] $\leftarrow$ Next

---
# First Order Derivative Approximation Filters
First order derivative approximation filters can be used to approximate derivatives, in a given, axis.
- Larger values, post-convolution, corresponds to edges.

Below would detect edges along the x-axis...
$$
T_{1\times3}=\begin{bmatrix}-1&0&1\end{bmatrix}
$$
Transposing it gives a filter which detects edges along the y-axis.

# Sobel Filters
Sobel filters have the ability to perform edge detection, by approximating first order derivatives, and smooth the image simultaneously.

Can also threshold the Sobel filter response: using a threshold value to only class pixels, post-convolution, as an edge if they are greater than the threshold value.
# Problems with Rudimentary Edge Detection Approaches
1) Picking single threshold to determine if a feature is or is not an edge does not give nice, continuous edges.
	- Can cause lots of discontinuity between lines.

2) Approaches, such as using a Sobel filter, result in edges which are thicker than they should be.
	- Edge detection wants to detect boundaries of an object not the entire object.
	- Edges should ideally be one pixel wide to precisely locate where the edge of an object is.
	- Thick edges make it hard to locate the boundaries of something.

