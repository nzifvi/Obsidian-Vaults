[[1,1 - Decision Trees]] $\leftarrow$ Back

---
# What are Classification Trees?
Classification trees = type of decision tree.
- Classification trees classify their decisions into categories (is X, is not X, etc.).

Classification trees can combine numeric data with non-numeric data (such as true or false values).

# Building Classification Trees
Given a data sample...

| Loves Popcorn | Loves Soda | Age | Loves Ice |
| ------------- | ---------- | --- | --------- |
| Y             | Y          | 7   | N         |
| Y             | N          | 12  | N         |
| N             | Y          | 18  | Y         |
| N             | Y          | 35  | Y         |
| Y             | Y          | 38  | Y         |
| Y             | N          | 50  | N         |
Choose what feature is being classified by the classification tree. This is the feature the classification tree will attempt to predict.
- Suppose classification tree is attempting to classify if somebody loves ice.

## 1) Choose Root Node (First Statement to be Tested)
All features, besides the one being tested, must be evaluated to see if it is the best possible root node.
- Done with the Gini impurity test.

To calculate Gini impurity, you must...
1) Run all samples through the currently built decision tree.
2) Keep counters of all possible outcomes of the feature being classified for all possible decisions.
	- Increment the counters based on the actual value of that data point's feature that is being classified


![[Pasted image 20251230002755.png]]

To perform a proper check on which decision is best to use, all leaves must have their GI calculated.
### Boolean Node Types
To calculate gini impurity for a leaf, calculate...

$$
GI=1-P(X=Outcome_1)^2 - P(X=Outcome_2)^2+...+P(X=Outcome_n)^2
$$
For above example, where the parent node is loves popcorn...
$$
GI_{(LOVES POPCORN, TRUE)}=1-P(X=Yes)^2-P(X=No)^2
$$
$$
P(X=Yes)=\frac{1}{1+3} = \frac{1}{4}
$$
$$
P(X=No)=\frac{3}{1+3}=\frac{3}{4}
$$
$$
GI_{(LOVES POPCORN, TRUE)}=1-\biggr(\frac{1}{4}\biggr)^2-\biggr(\frac{3}{4}\biggr)^2= \frac{3}{8}
$$
$$
GI_{(LOVES-POPCORN, FALSE)}=1-P(X=Yes)^2-P(X=No)^2
$$
$$
P(X=Yes)=\frac{2}{2+0}=1
$$
$$
P(X=No)=\frac{0}{2+0}=0
$$
$$
GI_{(LOVES POPCORN, FALSE)} = 1 - P(X=Yes)^2 - P(X=No)^2
$$
$$
GI_{(LOVES POPCORN, FALSE)} = 1 - (1)^2 - (0)^2 = 0
$$
Once all leaves GI's have been solved, the total gini impurity, TGI, for a decision can be solved...
- TGI is a weighted average of gini impurities.

Let...
- $Sum_x$ denote the sum of outcomes for leaf x.

For a decision tree with n leaves...
$$
TGI = \frac{Sum_1}{Sum_1+...+Sum_n}GI(Leaf_1)+\frac{Sum_2}{Sum_1+...+Sum_n}GI(Leaf_2)+...+\frac{Sum_n}{Sum_1+...+Sum_n}GI(Leaf_n)
$$

## Numeric/Continuous Node Types
When handling numeric or continuous nodes involved in their decision, calculating gini impurity scores has a different approach.

1) Order all numeric data in ascending order.

| Age | Loves Ice |
| --- | --------- |
| 7   | N         |
| 12  | N         |
| 18  | Y         |
| 35  | Y         |
| 38  | Y         |
| 50  | N         |
Becomes...

| Age | Loves Ice |
| --- | --------- |
| 7   | N         |
| 12  | N         |
| 18  | Y         |
| 35  | Y         |
| 38  | Y         |
| 50  | N         |
2) Calculate the average between adjacent data outcomes in the feature...

$$
\frac{7+12}{2}=9.5
$$
3) Using that average, use it as a decision...
![[Pasted image 20251230005136.png]]

Then calculate GIs of leaves and then TGI.

4) Repeat process for all possible averages.

5) Pick the lowest TGI. Decision with lowest TGI results in being chosen as node.


## 2) Choosing Next Nodes
Per iteration, a feature will no longer be available to be a new decision as it will be a parent decision of the current node.
- Next nodes done by branching from the current node that has been confirmed.
- This process of branching is repeatedly done until the TGI equals 0.

To determine the next decision to make...
1) Test all remaining possible features to be part of a decision, using TGI calculations just like before.
2) Lowest possible TGI is chosen to branch from the current decision.

A leaf node exists WHEN it's GI is equal to 0.

# Problems with Classification Trees
