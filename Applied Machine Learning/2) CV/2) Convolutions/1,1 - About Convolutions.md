[[2 - About Masks]] $\leftarrow$ Next

---
# What are Convolutions?
Convolutions are a type of operation in signal/image processing.
- Some form of convolution is used in almost every computer vision application.
- Convolution hypothesised to be good model for how low-level biological visual processing works.
- Convolutional Neural Networks (CNNs) = big part of deep learning. Convolutional part enables impressive results for multiple tasks.

Simple convolutional filters can be used for...
- Edge detection.
- Image denoising.
- Edge enhancement/sharpening.
- Object localisation

Abstractly, a convolution is like applying a function simultaneously to an area of pixels in an image.
- Convolution isn't a pixelwise operation.
- Convolutions are applied to neighbourhoods of pixels: taking the weighted sum of a neighbourhood with the dimensions of said neighbourhood defined by the mask and what indices are currently being visited.


The way the function is applied is by a sliding window: only a sub-image of the image is seen per execution of the function.

# How Convolutions Work
Convolution is performed on a 2d matrix, representing an image in a given channel, using a mask.
- Mask aka weight array, operator, kernel.

![[Pasted image 20260120164030.png]]

First, values of mask are flipped to create a TEMPLATE:
- signs inverted

![[Pasted image 20260120164146.png]]

Template is slid across the matrix, incrementing by 1 each time a convolution is finished.
![[Pasted image 20260120171025.png]]

To convolute, the elements the template is currently over are multiplied by their corresponding value in the template.
- Can create a submatrix of the matrix, with equal dimensions to the template, and then replace the current index of the mask with the result of the operation.

Their sum is taken and then stored in the current position of the mask:

![[Pasted image 20260120171137.png]]

