[[5 - Dynamic Range]] $\leftarrow$ Back

---
# How do Colour Images work?
Colour images work the same as a grayscale image, except they have 3 channels: a red, green, and blue channel.
- Each pixel has a red, green, and blue component referred to as channel.
- The three channels superimposed allow for 255^3 possible colours to exist if only allowing integer values of intensity in each channel.

An image still has a height and width, denoting an area of pixels. All that is different is that...
- Grayscale images have 1 channel.
- Colour images have 3 channels.

## Colour Images in OpenCV
In OpenCV, when a coloured image is loaded into an ndarray, the dimensions are structured as:
$$
Array[rowIndex, colIndex, channelIndex]
$$
- row and col define an area of pixels.
- each pixel has 3 channels: representing a red, green, and blue channel.

