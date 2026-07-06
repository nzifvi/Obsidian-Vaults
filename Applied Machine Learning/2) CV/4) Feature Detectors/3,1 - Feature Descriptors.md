[[2,2 - Response Functions]] $\leftarrow$ Back
[[3,2 - Scale Invariant Feature Transform]] $\leftarrow$ Next

---
# What are Feature Descriptors?
Feature descriptors are a compact representation of image information surrounding a detected feature.
- Feature descriptors uniquely represent the area about a detected feature

Feature descriptors must...
1) Be DISCRIMINATIVE
	- Contain enough information that enables one feature to be uniquely identified from all other detected features in an image or across many different images.

2) Be COMPACT
	- Able to be represented as a vector

Common feature descriptors are...
1) Raw pixel patch
	- Pixel intensity values in a small window about the detected feature.
2) Intensity gradients
	- Direction and magnitude of brightness changes nearby about the detected feature.
3) Colour histograms
	- Distribution of colours in a window about the detected feature.
4) Edge orientations
	- Which directions edges, in a window about the detected feature, point to.

## Issues with Common Simple Feature Descriptors
### Issues with raw pixel patch
1) Not robust to lighting changes (not photometric invariant)
	- Brighter or darker image of the same scene will produce different pixel values.
	- Causes the same feature, across different images, to not be considered as the same.
2) Not rotation invariant.
	- If window is rotated, the feature descriptor changes.
3) Not scale invariant.
4) High dimensionality
	- A $n\times n$ window results in $n^2$ values.
	- Dimensionality increases as n approaches infinity.

### Issues with intensity gradients
1) Sensitive to noise
	- Small amounts of noise in pixel values can significantly change gradient values: distorting feature descriptor.
	- May potentially cause feature descriptor in 1 image to be entirely different than a feature descriptor, of the same feature, in another image.
2) Not rotation invariant
	- Gradients are direction dependent.
	- Rotating the image changes the descriptor.
	- A feature descriptor in a rotated image will not describe the same feature in a non-rotated version of the image.


### Issues with colour histograms
1) Loses spatial information
	- 2 very different looking windows could have equivalent colour distributions.
	- May falsely flag a feature in one image to be the same as a different feature in another image.
2) Sensitive to lighting changes
	- Different lighting conditions in the environment alters the value of colours.
3) Not useful for grayscale images.

### Issues with edge orientations
1) Sensitive to noise
	- Noise in an image can cause a feature descriptor to observe false edges or ignore real ones.
2) Not scale invariant.
	- Edges look different at different scales.
	- Methods exist to solve this.
3) Quantisation issues
	- Grouping orientations into bins in a histogram loses highly precise directional information.