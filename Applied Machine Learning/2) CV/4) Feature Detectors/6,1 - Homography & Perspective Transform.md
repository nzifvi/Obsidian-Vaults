[[5 - Matching Features]] $\leftarrow$ Back
[[6,2 - RANSAC]] $\leftarrow$ Next

---
# What is Homography
Homography is a mathematical transformation that maps points from one flat plane to another flat plane.
- Flat plane may differ in orientation. Process of homography aligns them.
- Act of performing homography between 2 planes aka perspective transform.

$$
\vec{v}'=\begin{bmatrix}x'\\y'\\1\end{bmatrix}, \vec{v}=\begin{bmatrix}x\\y\\1\end{bmatrix}
$$

$$
\vec{v}' \textasciitilde H\vec{v}
$$
~ means "equal up to scale"
- 2D coordinates cannot represent perspective: do not represent the idea that parallel lines meet at infinity.
- Homogeneous coordinates solve 2D coordinates being unable to represent perspective by adding a third ordinate.

$$
(x,y) \rightarrow (x,y,1)
$$
- Equal scale means that the 2D coordinates remain equivalent up to any scale as they can always be recovered by dividing the coordinate by the value of the homogeneous ordinate.

# Perspective Transforming 2 Images

## 1) Produce Homography Matrix
`cv2` provides a function which estimates the homography between 2 lists of points.
- Used to perspective transform 2 images.

Below is the recommend parameters to change for `findHomography` function call.
- Others exist that can be modified.

```python
M, mask = cv2.findHomography(
	srcPoints,
	dstPoints,
	method,
	confidence
)
```

srcPoints:
- Coordinates of the points in the original plane
- Is a 3d numpy.ndarray

```
[
	[
		[x1 y1]
		[x2 y2]
		...
		[xn yn]
	]
]
```

dstPoints
- Coordinates of points in the target plane.
- Is a 3d numpy.ndarray

```
[
	[
		[x1 y1]
		[x2 y2]
		...
		[xn yn]
	]
]
```

method
- Integer flag used to control which method is used to estimate a homography matrix. Possible methods are:
	- 0
	- cv2.RANSAC
	- cv2.LMEDS
	- cv.2RHO

confidence
- Let $\alpha$ denote confidence
$$
\alpha \in \mathbb{R} | 0 \leq \alpha \leq 1
$$

## 2) Perspective Transforming
An image, represented as a matrix, has a number of rows (how many vertical pixels) and columns (how many horizontal pixels)

$$
I_{r\times c}
$$
```python
r, c = i.shape
```

`cv2` provides a function which performs perspective transformations on a Homography matrix
- called `perspectiveTransform`

```python
cornerPoints = np.float32(
	[
		[0, 0], [0,r-1], [c-1, r-1], [w-1, 0]
	]
).reshape(-1, 1, 2)

dst1 = perspectiveTransform(
	src = cornerPoints,
	dst = M
)
```

src
- Coordinates of the vertices of the source image.

dst
- Coordinates of the corresponding vertices in the destination image.

