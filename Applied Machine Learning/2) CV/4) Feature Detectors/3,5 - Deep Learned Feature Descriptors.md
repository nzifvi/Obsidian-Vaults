[[3,4 - Binary Robust Independent Elementary Features]] $\leftarrow$ Back
[[4 - Comparing Feature Descriptors]] $\leftarrow$ Next

---
# What are Deep Learned Feature Descriptors?
Deep Learned Feature Descriptors, DLFD, uses CNNs to create feature descriptors directly from windows about a detected feature.

CNN produces a descriptor vector, $\vec{D}(x)$, which is a compact, learned representation of the window about a detected feature.
- CNN learns which bits of information in the local window are most useful to uniquely identify that feature across multiple images.

$$
\vec{D}(x)=\begin{bmatrix}d(x)_1\\...\\d(x)_m\end{bmatrix}
$$

# Siamese Architecture
## Properties of Siamese Architecture NNs
A Siamese architecture is a twin neural network architecture.
- Contains $\geq 2$ individual neural networks and forms one massive overall one.

![[Pasted image 20260324103755.png]]

The individual neural networks in a Siamese architecture...
- Share the same weights.
- Receive different inputs.
- Produce outputs that are compared against each other.

Weights are shared between the individual neural networks to enforce symmetry.
- If the order of inputs are swapped, the output is still the same.


$L_2$ is the Euclidian distance between 2 feature descriptor vectors produced by the Siamese CNN.
- Measures how similar feature descriptors are
$$
L_2 = \sqrt{\sum_{i=1}^{m}\biggr[\biggr(d(x_1)_i-d(x_2)_i\biggr)^2\biggr]}
$$
$\text{As } L_2 \rightarrow 0, \text{feature descriptors are more similar}$
- Feature descriptors likely describe the same feature.

$\text{As } L_2 \rightarrow \infty \text{, feature descriptors are less similar}$
- Feature descriptors are less likely to describe the same feature.

## Training NNs with Siamese Architecture for to produce DLFD
Siamese CNN, through training, learns a mapping function.
- Maps a local window, about a feature, to a feature descriptor which can be used to uniquely identify that feature across multiple images

Let...
- $W_{n^2}$ denote a window about a detected feature.
- Let $\vec{D}(I_{x,y})$ denote the resulting feature descriptor vector of a feature, at position $(x,y)$, in the image $I$.

$$
f:W_{n^2} \rightarrow \vec{D}(I_{x,y})
$$

