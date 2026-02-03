[[4,1 - Arithmetic Operations on Image Variables]] $\leftarrow$ Back
[[4,3 - Histogram Equalisation]] $\leftarrow$ Next

---
# What is a Nonlinear Intensity Change?
Instead of adding a scalar value to each pixel's intensity, a nonlinear operation change typically alters the existing pixel's intensity to some power or alters ALL of the pixels by differing amounts.
- Gamma Correction does this.
- Thresholding is another example of a non linear operation
# Gamma Correction
Gamma correction, a nonlinear intensity change, adjusts the intensity of pixels in an image 
$$
I_{out}=(I_{in})^\gamma
$$
- $I_{in}$ is the normalised intensity, $[0, 1]$, of the pixel
- $I_{out}$ is the output of the gamma correction process.
- $\gamma$ is the scalar value that determines the shape of the change.

If...
- $\gamma < 1$ THEN ENCODING/BRIGHTENING
	- Dark areas of image are "stretched" (expanded), making shadow details easier to see
	- Image looks brighter
- $\gamma > 1$ THEN DECODING/DARKENING
	- Dark areas are "compressed", highlights are expanded.
	- Image looks darker and often higher in contrast.
- $\gamma = 1$ THEN NO CHANGE

```python
import matplotlib.pyplot as pyplot
import cv2
import numpy

imgFilePath = r"C:\Users\benja\OneDrive\Pictures\grayscaleImage.jpg"

img = cv2.imread(imgFilePath)
normalisedImage = img / 255.0
gammaCorrectedImage = numpy.power(img, 0.125)

pyplot.figure(figsize=(12, 6))
pyplot.subplot(1, 2, 1)
pyplot.imshow(img)
pyplot.title("Non-gamma Corrected Image")

pyplot.subplot(1, 2, 2)
pyplot.imshow(gammaCorrectedImage)
pyplot.title("Gamma Corrected Image")

pyplot.show()
```

# Thresholding
Thresholding is a nonlinear operation that alters the intensity of pixels, in an image, conditionally.
- Based on a given threshold value.

Let $T$ denote threshold value.

- If $I_{current}$ < T,  let $I_{new}$ = T
- If $I_{current} > T$, let $I_{new}$ = T

Can do one at a time.

