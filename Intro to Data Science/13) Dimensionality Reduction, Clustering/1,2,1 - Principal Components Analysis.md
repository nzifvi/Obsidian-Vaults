[[1,1 - Dimensionality Reduction]] $\leftarrow$ Back

---
# 1) What is Principal Components Analysis (PCA)?
Form of unsupervised learning that aims to reduce the dimensionality of multivariate data sample whilst preserving as much relevant information as possible.
- Used extensively in ML and data science to detect lower dimension structures in a sample and aid model training.


PCA transforms a given data sample into a hierarchical coordinate system based on input data sample.
- Enables new components to be ranked so that the most informative dimensions can be preserved.
- Data sample can then be transformed into the new coordinate system which has a reduced no. of dimensions.


# 2) How does PCA work?
PCA measures the variance between features in the same dimension of the sample: allowing it to determine how important each component can be.
- Higher variance in a given dimension means that the dimension is more influential in the output of a function.

If the variance between features in a dimension is very low, that dimension is less important.
- If all possible values of a feature in a given dimension are equivalent, the variance is 0. That dimension can be outright disregarded.

PCA occurs in multiple phases:
1) Pre-processing
2) Compute covariance matrix of input data to identify correlations.
3) Compute eigenvalues and eigenvectors of covariance matrix to identify principal components.
4) Arrange eigenvectors in order of their eigenvalues and select p components.
5) Project input data onto principal components to finally transform the input data sample.

## 2.1) Pre-processing
Data sample MUST be normalised for PCA to properly work.
- It computes variance about the origin.

Each feature is transformed into it's z-score equivalent by.
- Let $x$ be an outcome of a given feature in the sample.
$$
z = \frac{x-\mu}{\sigma}
$$
- $\mu$ is the mean of that feature in the sample
- $\sigma$ is the std. dev of that feature in the sample.

Normalising the data sample ensures comparisons are fair since they are all put onto a standardised scale.
- PCA only cares about directions, not magnitudes.

## 2.2) Compute Covariance Matrix to Identify Correlations

$$
\Sigma = \begin{bmatrix}  
var(x_{1}) & cov(x_{1}, x_{2}) & ... & cov(x_{1}, x_{n})\\  
cov(x_{1}, x_{2}) & var(x_{2}) & ... & ... \\
... & ... & ... & ... \\
cov(x_{1}, x_{n}) & ... &...& var(x_{n})
\end{bmatrix}
$$
Covariance matrix is a matrix which summarises the correlations between all possible pairs of variables and each with itself.

When applying PCA, idea is to...
1) Change coordinates by rotating the axes.
	- Done such that the off diagonal co-variance terms are zero. New features are uncorrelated.

2) Rank the variances of newly defined features in new coordinate system.

3) Select the features with p largest variances. p is how many features should be kept.

4) Project input data onto principal components.
	- Forms new representation of the data where the new representation has p dimensions.

## 2.3) Compute Eigenvectors and Eigenvalues of the Covariance Matrix.
[[1,2,2 - Solving Eigenvalues and Eigenvectors]] $\leftarrow$ How to solve for eigenvalues and eigenvectors.

To solve the directions of the maximum variance, eigenvalues and eigenvectors must be solved.
- Eigenvectors are orthogonal to each other: pointing in the directions of maximum variance.
- An eigenvector's corresponding eigenvalue are proportional to the amount of variance captured in that eigenvector's direction.

Let...
- $M_{n^2}$ be a square matrix of $n$ rows, $n$ columns.
- $\lambda$ be a constant.
- $\vec{e}$ be a non-zero column vector.

$\lambda$ is an eigenvalue of M, $\vec{e}$ is the corresponding eigenvector if and only if...
$$
M\vec{e}=\lambda\vec{e}
$$

## 2.4) Select the features with p largest features.
Take first p eigen vectors as principal features if the input must be reduced to a dimension of p.


# 3) Advantages and Disadvantages of PCA

## 3.1) Advantages of PCA
1) Noise Reduction:
	- Eliminated components with low variance, which are likely to be uninformative, will be removed: reducing possible sources of noise in the data sample.

2) Data Compression:
	- Manages to approximately represent the same data sample to a good degree of accuracy with fewer components.
	- Reducing amount of storage and processing for that data sample.

3) Outlier Detection:
	- Makes it easier to spot outliers in a data sample.

4) Reduces Overfitting:
	- Less redundant data = less of an opportunity to make decisions based on noise in the data sample.

5) Improves Accuracy:
	- One feature that combines multiple noisy yet correlated features means the accuracy of models improve.

## 3.2) Disadvantages of PCA
1) Information loss might be too much and cause the transformed data sample to no longer be approx. accurate to the original data sample.

2) PCA assumes linear relationships between features.
	- May struggle with non-linearly related features

3) PCA process is impacted by outliers in the data sample, since it relies on the mean during the pre-processing phase.

4) Principal components may be difficult to interpret.
	- Dimensions post PCA are no longer just measurements. They are something else.

# 4) When and When Not to use PCA
PCA works well when the sample has a Gaussian distribution.
- Use when sample has a Gaussian distribution.

Certain things break PCA, resulting in it causing issues:
- If there is a non-linear relationship between components, PCA doesn't work well.
	- PCA will overestimate input dimensionality.
- PCA has a high bias towards high levels of variance between components in a sample.
	- PCA, in the calculation of the eigenvectors, will make mistakes.



