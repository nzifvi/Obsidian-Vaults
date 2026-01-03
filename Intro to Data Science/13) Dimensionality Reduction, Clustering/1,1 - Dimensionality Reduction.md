
---
# 1) What is Dimensionality Reduction?
Dimensionality reduction is the process of reducing the no. of dimensions (features) that are used to represent data.


Why do dimensionality reduction?
1) It is computationally expensive to store and process data with a large. no of dimensions.

2) Overfitting is less likely if there are fewer parameters for a model to learn.

3) One feature that combines several noisy yet correlated features means the accuracy of a model improves.

4) It is impossible to visualise high-dimension spaces. Humans can only really visualise 2D or 3D.
	- Dimensionality reduction provides a way to keep the no. of dimensions in data easy to visualise by humans.

![[Pasted image 20251201091901.png]]
- Questionnaire results in 24 features of a data point in a sample. Therefore it has 24 dimensions.
- 24 dimensions impossible to visualise.
- By performing dimensionality reduction, 24D reduced into 2D and then can be visualised.
# 2) Why perform Dimensionality Reduction
As dimensionality increases, the volume of space grows exponentially quickly.
- Finite dataset becomes very sparse as the no. of dimensions increases.
- More data must be collected to populate the data set so that accurate descriptive statistics can be produced.

E.g: K-Means Clustering.
- Algorithm works based on distances between things we want to classify.
- For 2 points x,y transformed into vectors.

$$
distance(\vec{x}, \vec{y}) = \sqrt{\sum_{i=1}^{n}\biggr[(y_{i}-x_{i})^2\biggr]}
$$
- $size(\vec{x}) = n$, $size(\vec{y} = n$

- If features $x_1, y_1$ and $x_2, y_2$ are very different, as the number of dimensions, $\vec{a}|size(\vec{a}) = n$, approaches infinity the difference between these features are watered down.

- Distances in higher dimensions lose meaning.


# 3) How is Dimensionality Reduction performed?
Dimensionality reduction can be done 1 of 2 ways:
1) FEATURE SELECTION:
	- Dropping, aka, removing features.
2) FEATURE PROJECTION:
	- Creating new features as a linear combination of existing features: compressing multiple features into 1.

## 3.1) Dimensionality Reduction Algorithms
GOAL: transform the data from a higher dimension space into a lower dimension space.
- E.g: transform a 4D space into a 3D space.

Some feature projection dimensionality reduction algorithms are:
1) Principal Components Analysis PCA.
	- [[1,2,1 - Principal Components Analysis]]

2) Non-negative Matrix Factorisation NMF.

3) Linear Discriminant Analysis LDA.

4) T-distributed Stochastic Neighbour Embedding t-SNE

5) Uniform Manifold Approximation and Projection UMAP

6) Autoencoders