[[3 - Types of Templates]] $\leftarrow$ Back
[[5 - scipy convolve2d]] $\leftarrow$ Next

---
# Issue with Boundaries
When the template touches a boundary, the origin of the template CANNOT advance any further else an out of bounds index will occur:
![[Pasted image 20260120185321.png]]
![[Pasted image 20260120185359.png]]

The convolution of rows, as well as columns, must be stopped at certain points to prevent the above issue occurring. Multiple ways exist.

# Ways to Handle Boundaries
### 1) Make output array of convolution smaller than the input array. This way, the template never goes out of bounds.
![[Pasted image 20260120185851.png]]

Let...
$$
outputArray.rows=inputArray.rows - mask.rows + 1
$$
$$
outputArray.cols = inputArray.cols - mask.cols + 1
$$
Define an output array:
$$
outputArray[outputArray.rows, outputArray.cols]
$$
![[Pasted image 20260120190018.png]]

Then iterate over the input array using the output array rows and columns as the bounds of the loops.
- Prevents going out of bounds.
- However, each convolution WILL reduce the size of the image.


```python
def convolute(inputImage, mask):
	# flip the mask so that it becomes a template...
	rowBound = inputImage.shape[0] - mask.shape[0] + 1 # for x axis...
	colBound = inputImage.shape[1] - mask.shape[1] + 1
	outputImage = numpy.zeros((rowBound, colBound)) # create empty output array
	
	for x in range(rowBound):
		for y in range(colBound):
			conv = 0
			for i in range(mask.shape[0]): # along rows...
				for j in range(mask.shape[1]): # along columns...
					conv += mask[i, j] * inputImage[x + i, y + j]
			outputImage[x, y] = conv
			
	return outputImage
```



### 2) Assume the data at the boundaries are reflected.

### Other ways exist yet they are not as safe.