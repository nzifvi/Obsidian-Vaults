[[2,2 - Clustering Algorithms]] $\leftarrow$ Next

---
# What is Clustering?
Clustering is the act of learning a model from unlabelled data points in a given sample.

Learning is unsupervised.
- No labelling function exists. All you have are just data points.

Clustering detects patterns and structures within data.
- Clustering is especially useful when it is unknown what to look for.

## Clustering vs. Classification
In classification, the data points in a sample have a label. Classification attempts to learn what differentiates these labels to properly classify future, unseen data.

In clustering, there are no known labels for the data samples. They are unknown or undefined. Clustering attempts to learn the labels as well as what differentiates these labels.


# How does Clustering Work
Given a sample...
![[Pasted image 20251229203222.png]]

The goal of clustering is to separate the data points of a sample into separate clusters.
- Each cluster corresponds to a label that the process has "discovered" and come to the conclusion that it is different from other clusters.
- Data points are clustered based on how similar they are.

Similarity is based on distance from other points.
- If a data point is distant from another, it is dissimilar. 
- If a data point is not really distant from another, it is similar.

## Measures of Similarity 
Some measures of similarity are...
1) Euclidian Distance
