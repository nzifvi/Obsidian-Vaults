[[2 - Descriptive Statistics of Gray-Scale Images]] $\leftarrow$ Next

---
# Images as Arrays
Any given image...

![[Pasted image 20260119210519.png]]

... can be represented as a 2D matrix where each element is a pixel of the image.

$$
A_{RowNo \cdot ColNo}
$$
In OpenCV, an image is represented as a 2D array.
$$
A[RowNo, ColNo, channelNo]
$$
- RowNo = no. of rows in image.
- ColNo = no. of columns in image.

# Pixels of a Grayscale Image
Pixels, in a grayscale image, have a singular scalar value which represents their intensity.
$$
p\in [0, 255]
$$

# Normalising a Gray-Scale Image
Gray-scale images have pixels with an intensity value that ranges from $[0, 255]$
- Normalising a gray-scale image means to convert the range from $[0, 255]$ to $[0,1]$
$$
Img_{normalised}= \frac{Img}{255}
$$
