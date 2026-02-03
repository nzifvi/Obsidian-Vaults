[[3,1 - Images as Histograms]] $\leftarrow$ Back
[[4,2 - Nonlinear Operations]] $\leftarrow$ Next

---
# Changing Pixel Values
## By Scalar
Works by doing...
$$
newImg = Img <op> value
$$
...where
- newImg is an image type variable.
- img is an image type variable.
- op is an arithmetic operator
- value is a scalar value

```python
import matplotlib.pyplot as pyplot
import cv2
import numpy

imgFilePath = r"C:\Users\benja\OneDrive\Pictures\grayscaleImage.jpg"

img = cv2.imread(imgFilePath)

pyplot.imshow(img)
pyplot.show()
```


```python
pyplot.imshow(img-100)
pyplot.show()
```

```python
pyplot.imshow(img*4)
pyplot.show()
```
