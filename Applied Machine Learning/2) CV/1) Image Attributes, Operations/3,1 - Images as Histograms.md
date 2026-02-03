[[2 - Descriptive Statistics of Gray-Scale Images]] $\leftarrow$ Back
[[4,1 - Arithmetic Operations on Image Variables]] $\leftarrow$ Next

---
# Images as Histograms
Descriptive statistics about an image are limited about what they can represent about said image.

A more flexible description of an image is a histogram.
- Histogram splits image into discrete bins (value ranges) and counts the number of occurrences in each bin.

Given an image with intensity values over the range $[0, L-1]$, a histogram is a function...
$$
h(r_k)=n_k
$$
- $r_k$ is the k$^{th}$ intensity value $\in [O, L-1]$
- $n_k$ is the number of pixels in the image with an intensity of $r_k$

Image histograms...
1) Provide a global description of an image's contents.
2) Summarise how much of which colour, denoted by a bin, is in an image.
3) Discards all spatial relationship data (patterns, textures, etc.) STRICTLY FOCUSES ON HOW MUCH OF WHAT COLOUR APPEARS IN AN IMAGE.

```python
import matplotlib.pyplot as pyplot
import cv2
import numpy

imgFilePath = r"C:\Users\benja\OneDrive\Pictures\grayscaleImage.jpg"

img = cv2.imread(imgFilePath, 0)

pyplot.figure(figsize=(10, 6))
pyplot.hist(img.flatten(), density=True, bins=range(256))
pyplot.show()
```


# Choosing Number of Bins
Sometimes it is best to use the exact number of bins, 256, and other times it is best to used a reduced no. of bins.
- 256 due to a pixel having a range of values $[0, 255]$

Use 256 bins when...
- Wanting high precision: each intensity shown.
- Working with grayscale/medical images.
- Performing technical analysis/editing checks.

Use reduced bins $[10, 30]$ when...
- Wanting easy to read data.
- Checking if an image is mostly bright, mostly dark, or mostly mid gray.


# Histograms as Features
[[3,2 - Histograms as Features]] $\leftarrow$ Next