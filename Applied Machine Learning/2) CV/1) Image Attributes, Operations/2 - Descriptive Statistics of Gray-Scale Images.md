[[1 - Grayscale Images as Arrays]] $\leftarrow$ Back
[[3,1 - Images as Histograms]] $\leftarrow$ Next

---
# Descriptive Statistics of Gray-Scale Images
From an image, the following descriptive statistics can be computed:
- Max
- Min
- Mean
- Std-Dev
... from the pixels of the image

Done using numpy library with Image type variable as a parameter. 

```python
import matplotlib.pyplot as pyplot
import cv2
import numpy

imgFilePath = r"C:\Users\benja\OneDrive\Pictures\grayscaleImage.jpg"

img = cv2.imread(imgFilePath)
pyplot.imshow(img)

print(numpy.max(img))
print(numpy.min(img))
print(numpy.mean(img))
print(numpy.std(img))
```


Can produce these descriptive statistics for:
1) Global image (the image itself)
2) Sub-Image (a subsection of the global image)

# Calculating Descriptive Statistics for Sub-Images
Can select a sub-image from a given image by specifying the boundaries of:
- startRow to endRow
- startCol to endCol

```python
startRow = 100
endRow = 200
startCol = 200
endCol = 300

print(
	numpy.max(img[startRow:endRow, startCol:endCol])
)
```
