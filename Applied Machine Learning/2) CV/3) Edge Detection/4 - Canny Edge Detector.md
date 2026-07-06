[[3 - Edge Detection and Spatial Scale]] $\leftarrow$ Back
[[5 - Laplacian Template]] $\leftarrow$ Next

---
# What is the Canny Edge Detector?
Canny edge detector is known as the most successful edge detection devised so far.
- Combines several ideas to give pretty reliable edge detection results.

Canny edge detection applies below steps sequentially:
![[Pasted image 20260317150603.png]]


## Step 1) Gaussian Smoothing
Image is smoothed, using Gaussian smoothing, to reduce local noise.
- Gradient estimation strongly impacted by image noise (high spatial frequency)
- High spatial frequency can lead to many false positives when estimating gradients.

## Step 2) Computing Gradients
Using Sobel filter, gradients are estimated in the smoothed image.
- Information is used to estimate the strength and orientation of edges.

## Step 3) Non-maximum Suppression
Non-maximum Suppression is used to make detected edges, from Sobel filter, more responsive.
- Thins the edge map produced by prior stage.

Steps:
1) Identify direction of an edge.
	- Each pixel of edge map encodes gradient in both x and y.
	- Using trigonometry, the angle of the edge can be calculated:

$$
\theta(x,y)= tan^{-1}\biggr(\frac{M_{y}(x,y)}{M_{x}(x,y)}\biggr)
$$
In practice, better to use $atan2$ to avoid sign issues due to needing to know what quadrant the angle is in.
$$
\theta{(x,y)} = atan2\biggr(M_{y}(x,y),M_{x}(x,y)\biggr)
$$
2) For each pixel, look perpendicular to the line of the edge and test if this pixel is a local maximum.
	- Requires interpolation again: must calculate gradient response at new locations which may not be part of the image.

![[Pasted image 20260317151704.png]]

$$
M_1 = \frac{M_y}{M_x}M(x+1,y-1)+\frac{M_x-M_y}{M_x}M(x,y-1)
$$
$$
M_2=\frac{M_y}{M_x}M(x-1,y+1)+\frac{M_x-M_y}{M_x}M(x,y+1)
$$
Calculate the magnitude of the gradient ($P_{x,y}$)
$$
P_{x,y}=\sqrt{M_{x}^2+M_{y}^2}
$$
If the pixel is not a local maximum...
$$
P_{x,y} \leq M_1 \wedge P_{x,y} \leq M_2 \Rightarrow P'_{x,y} = 0
$$
... let gradient magnitude of that pixel equal 0.

If pixel is a local maximum...
$$
P_{x,y} > M_1 \wedge P_{x,y} > M_2 \Rightarrow P'_{x,y}=P_{x,y} 
$$
... keep the value of the gradient magnitude.

## Step 4) Hysteresis Thresholding
Hysteresis Thresholding uses two edge strength thresholds to remove pixels, based on where they fall on the threshold.

Let below denote hysteresis threshold:
$$
[a,b]
$$
- a is the lower bound.
- b is the upper bound.

If...
1) Pixel's intensity is below the lower bound, it is removed.
$$
P_{x,y}<a \Rightarrow P'_{x,y}=0
$$
2) Pixel's intensity is above the upper bound, it is immediately kept.
$$
P_{x,y}>b \Rightarrow P_{x,y}' = 1
$$

3) If the pixel's intensity is within the threshold and there exists a path between a neighbouring pixel that is also within the threshold, it is kept.
$$
P_{x,y}>a \wedge P_{x,y}<b \wedge \exists path\biggr(P_{x,y},P_{x',y'}\biggr) \Rightarrow P_{x,y}=1
$$

# Implementing Canny Edge Detector
Annoying to set up yourself, just use `cv2.Canny`
```
cv2.Canny(
	img,
	lower_th,
	upper_th,
	sobel_template_size
)
```
