[[4 - Handling Boundaries]] $\leftarrow$ Back

---
# What is convolve2d?
convolve2d is a function member of the scipy signal module.
- Convolutes an input array using a mask which are BOTH given as inputs upon function's call.
- Returns the output array which is the result of the convolution.

convolve2d handles turning the mask into a template.

```
convolve2d(in1, in2, mode='full', boundary='fill', fillvalue=0)
```

## Parameters:
### in1
The input array desired to apply a mask to.
- Mandatory input. Should be an ndarray.
### in2
The mask itself.
- NOTE: convolve2d handles creating the template from the provided mask.
- Mandatory input. Should be an ndarray.

in2 MUST have equivalent no. of dimensions as in1.
- If an image, MUST have a mask per channel.
### mode
Determines the size of the output array
- Default is full

#### options:
1) full
	- Output is larger than input. Input is M x N, mask is m x n. Output is (M + m  1) x (N + n -1)
	- Use when not wanting to lose ANY information on the boundaries.
2) same
	- Output will have same size as input. 
	- Works by first calculating the convolution with full mode and then cropping the additional elements, leaving the original size.
	- Use when wanting to not increase sizes of a given dimension.
3) valid
	- Output is SMALLER than input.
	- Input is M x N, mask is m x n, then output is (M - m + 1) x (N - n + 1).
	- Use when wanting to avoid artifacts caused by zero-padding at boundaries.

### boundary
Controls how the boundary is handled.
- Default is fill option.
#### options:
1) fill
	- pad input arrays with fillvalue (has a default value of 0)
2) wrap
	- wraps around the boundary
3) symm

### fillvalue