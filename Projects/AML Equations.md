
---
# Near-duplicate Detection
$$
D = \{\vec{d}_1,...\vec{d}_{|D|}\}
$$
Let f denote a function which creates a local neighbourhood of points about $\vec{d}_i$
$$
f(\vec{d}_i, D)= \bigcup_{\vec{d}_j \in (D-\{\vec{d}_i\})}\biggr[g(\vec{d}_i, \vec{d}_j)\biggr]
$$
$$
g(\vec{d}_i, \vec{d}_j)=\begin{cases}
d_{j_1} < r \wedge ....\wedge d_j{_n} < r \Rightarrow g(\vec{d}_i, \vec{d}_j) = \vec{d}_j
\\
g(\vec{d}_i, \vec{d}_j) = \emptyset
\end{cases}
$$

Where...
- r denotes a radius about vector $\vec{d}_i$

Creates an $n^{th}$ dimension neighbourhood.
- $n$ is the number of dimensions in the fixed-length document vectors.

Fine tune r by noticing the increase in accuracy as the value of r increases.
- Should approximate a quadratic curve as the more strict r is, the more nonspam data is removed: decreasing model accuracy.
- Turning point of $h(r)$ (quadratic curve function) is optimal value of r where accuracy is highest 