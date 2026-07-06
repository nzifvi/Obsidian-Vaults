[[1 - About Face Alignment]] $\leftarrow$ Back
[[3 - Data Augmentation]] $\leftarrow$ Next

---
# 1) Template Matching with Shape Models
## Active Shape Models(ASM)
### What is ASM
ASMs aim to model the valid space of face shapes, using PCA, and then search for the best match in a new image by...
1) Looking locally around each facial feature for edge-like structures.
2) Constraining the shape of the image's shape to remain probable.
	- Probable shapes determined by the learned shape space.

### ASM Model
#### Training Data
Suppose we have M images with manually annotated facial features...
$$
M=\{I_1,...I_M\}
$$
$f$ is a function which produces manually annotated facial features: $S$
$$
f(I_1)=S_1 = \begin{bmatrix}
s_{(1,1)}&...&s_{(1,N)}\\
s_{(2,1)}&...&s_{(2,N)}
\end{bmatrix}
$$
The $k^{th}$ facial feature from a matrix is denoted as
$$
(s_{(1,k)},  s_{(2, k)})
$$

- $s_{(1, i)}$ represents the x-ordinate of the $i^{th}$ facial feature in an image.
- $s_{(2, i)}$ represents the y-ordinate of the $i^{th}$ facial feature in an image.

$$
\forall j, S_j \in \mathbb{R}^{2N}
$$
- $2N$ due to the fact that there are $N$ x-ordinates in one row and $N$ y-ordinates on the other.
- $N$ is the number of facial features per face.
#### Pose Variation Removal
Before computing any statistics from the M images with manually annotated facial features, pose variation must be removed.
- Pose variation = variance in the translation, rotation, and scale of pixels between 2 or more images.
- Removing pose variation ensures only shape variation remains: enabling face alignment.


$(\bar{x}_j, \bar{y}_j)$ defines the centroid (average pixel) of the facial features $S_j$ from image j.

$$
\bar{x}_j = \frac{1}{N}\sum_{i=1}^{N}s_{(1, i)}
$$

$$
\bar{y}_j = \frac{1}{N}\sum_{i=1}^{N}\biggr[s_{(2,i)}\biggr]
$$

$$
S_j' = S_j - \begin{bmatrix}
\bar{x_j}&...&\bar{x_j}\\
\bar{y_j}&...&\bar{y_j}
\end{bmatrix}
$$
$$
S_j' = \begin{bmatrix}
s_{(1,1)} - \bar{x}_j &...&s_{(1, N)} - \bar{x_j}\\
s_{(2,1)} - \bar{y}_j &...&s_{(2, N)} - \bar{y_j}
\end{bmatrix}
$$

#### Normalise all images to the same size
Measure the size of matrix j
$$
size_j = ||S'_j||_{F} = \sqrt{\sum_{k=1}^{N}\bigg[(s'_{(1,k)})^2+(s'_{(2,k)})^2\bigg]}
$$

Then normalise the matrix $S'_j$ by the size...
- Turns it into a unit matrix.

$$
\hat{S}_j = \frac{1}{||S'_j||_F}S'_j
$$


#### Rotation Alignment
Rotate all unit vector representations of facial features such that they have a common orientation.
- Most complex step: requires finding a rotation that best aligns each vector to a reference.

A reference shape matrix, $\hat{S}_{ref}$, is required
- Typically the first shape: $\hat{S}_1$
- Can be the average of all shape matrices: $\bar{\hat{S}}$
$$
\bar{\hat{S}}=\sum_{i=1}^{M}\bigg[\hat{S}_i\bigg]
$$
- Other ways to produce a reference matrix exist.

$$
H_j = \hat{S}_j(S_{ref}^T)
$$
- Produce $R_j$ via SVD on $H_j$
$$
S''_{j}=R_j\hat{S}_j
$$
#### Performing PCA
Perform PCA on vectors representations of the shape matrices: produced by flattening them.
$$
\vec{s}_j = flatten(S''_j) | \vec{s}_j \in \mathbb{R}^{2N}
$$
- Use numpy or scipy to do PCA on set of vectors.
## Active Appearance Models (AAM)
# 2) Regression-Based Approaches

# 3) Deep Learning Approaches