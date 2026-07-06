
---
# What is k-means Clustering?
k-means Clustering is a partition algorithm. It is one of the most simple partition algorithms which exist.
- Based on the idea of a circle's centroid.
- Circle is defined by a radius about a group of points.


# How does k-means Clustering Work?

## INITIALISATION STAGES:S
1) Select k, the number of clusters, to split the data into.
	 For a sample of n data points...
	 $$k \leq n \wedge k > 0$$
	- Chosen value of k is important. There will be k clusters at the end of the process.

2) Initialise the centroids of k clusters.
	- k centroids must be initialised to have a point.
	- Centroid is itself an $n^{th}$ dimensional coordinate. It will change during the iterative stages as more and more points become part of a centroid's cluster.
	- 2 methods are used to choose initial coordinates for the centroids of k clusters.

### 1) Naïve Initialisation
Select k points, $\vec{p}$ from the data set to be centroids with a uniform probability.
- Sensitive to bad luck: if 2 points too close to each other are chosen, naïve initialisation can cause poor convergence to a local minimum.
$$
Clusters=\{C_1, C_2\}
$$
$$
\forall C_j, C_j\in Clusters | P(Centroid(C_j) = \vec{p}) = \frac{1}{|D|}
$$
Where...
- D is the data set.
- $\vec{p}$ is a vector representation of a data point $\in D$.

NOTE: once a point is chosen to be a cluster. The same point CANNOT be used as another centroid.
### 2) k-means++
k-means++ attempts to improve naïve initialisation by modifying how all other centroids, besides the first, are chosen.

First: a first centroid is chosen from all data points, $\vec{p}$ with a uniform probability to be chosen.
$$
Clusters = \{C_1,...C_k\}
$$
$$
\forall \vec{p}, \vec{p}\in D |P(Centroid(C_1) = \vec{p}) = \frac{1}{|D|}
$$
Initial cluster is removed from remaining clusters to assign a centroid to...
$$
Clusters_{remaining}' = Clusters_{remaining} + \{C_1\}
$$
Initial point, chosen to be the initial cluster's centroid, is removed from centroid candidates...
$$
D' = D - \{Centroid(C_1)\}
$$
Assign the chosen point to a set of chosen centroids
$D_{centroids}$ = $D_{centroids} + \{Centroid(C_1)\}$ 

For each remaining data point, it's squared distance from the nearest already chosen centroid is calculated...
$$
\forall \vec{p_{candidate}}, \vec{p_{candidate}}\in D' \wedge \vec{p}\cancel{\in}D_{centroids}
$$
$$
MinimalCentroidDistance(\vec{p_{candidate}}) \text{min}_{\vec{p_{centroid}}\in D_{centroids}}\biggr(||\vec{p}_{candidate}-\vec{p}_{centroid}||^2\biggr)
$$
Then the probability of a candidate point, $\vec{p}_{candidate}$, is equal to...
$$
C_j \cancel{\in}Clusters'
$$
$$
P(Centroid(C_j)=\vec{p}_{candidate})=\frac{MinimalCentroidDistance(\vec{p}_{candidate})^2}{\sum_{\vec{p}\in (D')}\biggr[MinimalCentroidDistance(\vec{p})^2\biggr]}
$$
Continue this k times. Each point chosen to be a cluster, ensure that...
- It is added to $D'$ so it is not considered to be a candidate point again.

## ITERATIVE STAGES:
1) Centroid of the clusters are all updated.
	- Each cluster has a centroid: a point which is at the centre of that cluster.
	  
	- Centroid is itself a point (could be represented as a vector).
	  
	- To calculate a centroid, calculate mean of data points within that cluster

$$
Clusters = \{C_1,...,C_k\}
$$
$$
\forall C, C\in Clusters | C=\{\vec{p_1},..,\vec{p}_{|C|}\}
$$
$$
Centroid(C)=\frac{1}{|C|}\sum_{i=1}^{|C|}\bigg[\vec{p}_i\biggr]
$$


2) Reassign every point, in the data, to the cluster it is nearest to.
Let...
- $\vec{u}_j = Centroid(C_j)$

Each point, $\vec{p}_i \in D$, is reassigned by...
$$
C_j = \biggr\{\vec{p}_j\in D | j=\text{argmin}_{l\in\{1,...,k\}}||\vec{p_j}-\vec{\mu_l}||^2\biggr\}
$$

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
