[[3,5 - Deep Learned Feature Descriptors]] $\leftarrow$ Back

---
# How to compare Feature Descriptors
Feature descriptors are a vector of numbers.
- They can be compared via various methods.
- The comparison method used depends on what method was used to produce the feature descriptor

Let...
- $\vec{a}$ denote a feature descriptor 
- $\vec{b}$ denote another feature descriptor.

$$
\vec{a}=\begin{bmatrix}a_1 \\...\\a_N\end{bmatrix}, \vec{b}=\begin{bmatrix}b_1\\...\\b_N\end{bmatrix}
$$

SIFT and HOG feature descriptors use the sum of Euclidian or absolute distance between the elements of the feature descriptors

$$
Dist(\vec{a}, \vec{b})=\frac{1}{N}\sqrt{\sum_{i=0}^{N}\biggr[(a_i-b_i)^2\biggr]}
$$
NOTE:
- Feature descriptors are vectorised representations of histogram bins