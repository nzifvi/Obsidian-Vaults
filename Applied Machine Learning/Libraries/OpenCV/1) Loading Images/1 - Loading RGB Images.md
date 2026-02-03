[[2 - Loading Grayscale Images]] $\leftarrow$ Next

---
# How to load images
To load an image, `imread()` function is used with a file path of the image as it's parameter when called...

```python
import numpy
import cv2
import matplotlib.pyplot as pyplot

imgBgr = cv2.imread(r"C:\Users\benja\OneDrive\Obsidian Vaults\Applied Machine Learning\-\misha.png")
```

By default, openCV loads RGB images as BGR (channels are reversed).
- To get RGB, must CONVERT image using `cvtConvert()` function

## Converting channel types
```python
imgRGB = cv2.cvtColor(imgBgr, cv2.COLOR_BGR2RGB)
pyplot.subplot(1, 2, 1)
pyplot.imshow(imgBgr)

pyplot.subplot(1, 2, 2)
pyplot.imshow(imgRGB)

pyplot.show()
```
`cvtColor(img, conversionType)` expects two parameters:
1) img: an image type variable.
2) conversionType: a valid conversion type, listed as a flag in cv2 library.


# How are multi-channel images stored by OpenCV?
Multi-channel images are stored as 3D arrays.
- 1 dimension for pixel rows, another dimension for pixel columns.
- 1 dimension for channel (R, G, B, etc)...

OpenCV stores it specifically as...
$$
A[pixelRow][pixelCol][channel]
$$
- height of an image corresponds to the maximum value of $pixelRow$
- width of an image corresponds to maximum value of $pixelCol$

```python
pyplot.subplot(1,3,1)
pyplot.imshow(imgRGB[:, :, 0], cmap='Reds')

pyplot.subplot(1, 3, 2)
pyplot.imshow(imgRGB[:, :, 1], cmap='Greens')

pyplot.subplot(1, 3, 3)
pyplot.imshow(imgRGB[:, :, 2], cmap='Blues')

pyplot.show()
```
