
---
# What is k-means Clustering?
k-means Clustering is a partition algorithm. It is one of the most simple partition algorithms which exist.
- Based on the idea of a circle's centroid.
- Circle is defined by a radius about a group of points.


# How does k-means Clustering Work?

INITIALISATION STAGES:
- Select k points to act as initial centroids.
	 For a sample of n data points...
	 $$k \leq n \wedge k > 0$$
	- Chosen value of k is important. There will be k clusters at the end of the process.


ITERATIVE STAGES:
1) Centroid of the clusters are all updated.
	- Each cluster has a centroid: a point which is at the centre of that cluster.
	  
	- Centroid is itself a point. Each ordinate of the centroid must be calculated. For each dimension in the sample, there will be another ordinate to calculate.
	  
	- To calculate ordinate of a centroid, calculate mean of data points within that sample in the ordinate's dimension.

$$
Cluster_1 = \{\vec{p_1}, \vec{p_2}, \vec{p_3}\}
$$
$$
\vec{p_j} = p_{j_1}\hat{i}+p_{j_2}\hat{j} +...+p_{j_d}\hat{d}
$$
Sample has 2 dimensions. All centroids will be 2D.
$$
Centroid(Cluster_1) = (C_1, C_2)
$$

$$
C_1 = \frac{1}{|C|}\sum_{i=1}\biggr[p_{j_i}\biggr]
$$

2) Update the clusters based on the calculated centroids for all points in the sample.
	- For each point in the sample, calculate their distance to each cluster's centroid.

$$
Centroid(Cluster_1), Centroid(Cluster_2), Centroid(Cluster_3)
$$
	- Each point is added to the cluster it has the least distance between. 
		- If point is part of another cluster, it is removed and added to the new one.

3) Calculate new centroids. 
	- If all the new centroids of the clusters are the same as the old centroids: end the iterative process. Clustering has finished.

# Pros and Cons of k-means Clustering
## Pros
1) Fast:
2) Simple to implement.
3) Intuitive.

## Cons
1) Need to know/choose k before using k-means clustering.
	- An optimal k exists. One way to find the best k out of a set of possible k values is to try them all and select the best.

2) May converge on a local minimum rather than a global minimum.
	- k-means is a greedy algorithm. It may sometimes not produce a globally best solution.
	- Can somewhat fix this by repeated random initialisations over multiple runs of k-means.

3) Hard clustering
	- Each data point of the sample will only belong to one singular cluster.
	- Data points cannot be part of 2 clusters.

4) Flat Structure.
	- Due to k-means being a partition algorithm, it cannot capture possible subclusters which may be present in the sample.
	- May risk oversimplifying the structures in a data sample.

# k-means Optimisation
