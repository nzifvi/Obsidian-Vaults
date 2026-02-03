[[5,3 - Word Vectors]] $\leftarrow$ Back

---
# What are Co-occurrence Matrices?
A co-occurrence matrix, $C$, is a matrix which records how often words occur together via their features.
$$
C_{TargetWords \cdot Features}
$$
- Rows of C = no. of target words.
	- Each row forms a word vector for the target word.
- Columns of C = no. of features captured.
	- Each column is the frequency of a feature for the target word the row represents

![[Pasted image 20260201142904.png]]

$$
C_{5\cdot7}
$$
$$
c_{(cat, the)} = 1
$$