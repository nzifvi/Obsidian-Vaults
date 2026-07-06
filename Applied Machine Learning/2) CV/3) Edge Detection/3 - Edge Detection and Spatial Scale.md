[[2 - Rudimentary Edge Detection Approaches]] $\leftarrow$ Back
[[4 - Canny Edge Detector]] $\leftarrow$ Next

---
# Edge Detection and Spatial Scale
When detecting edges, the size of features (spatial scale) that you are looking for must be known
- Spatial scale = size of features is an image. Determines what can be seen.

Depending on the value of a spatial scale, different things can be seen.
- Small spatial scales may only detect single noisy pixels changing values.
- Medium spatial scales may only detect the edge of a window on a building.
- Large spatial scales may detect the outline of an entire building.


# Spatial Scale and Spatial Frequency
Spatial scale and spatial frequency are inversely proportional.
- As spatial scale increases, spatial frequency decreases.
- Spatial frequency measures how rapidly intensity changes across the space of an image.

Small spatial scale = high spatial frequency.
- Changes occur rapidly over short distances.

High spatial scale = small spatial frequency.
- Changes occur over long distances.

# Controlling Spatial Scale and Spatial Frequency
Gaussian smoothing is used to control spatial scale and frequency in an image.
- Gaussian smoothing is used to smooth edges: changing spatial frequency.

If a pixel has a sudden change in intensity compared to neighbouring pixels, Gaussian smoothing can smooth over that intense pixel: decreasing it based on neighbouring pixels so that it is similar to them.
- Decreases spatial frequency which increases spatial scale.

The standard deviation, $\sigma$, of the Gaussian controls how much spatial frequency is removed.
- As $\sigma \rightarrow \infty$, the Gaussian becomes wider, and the Gaussian removes more high frequencies.
- As $\sigma \rightarrow \infty$, Gaussian becomes smaller, and Gaussian removes fewer high frequencies.
	- Decreasing $\sigma$ allows for finer details to survive.