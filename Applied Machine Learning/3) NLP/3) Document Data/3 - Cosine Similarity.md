[[2 - Document Vectors]] $\leftarrow$ Back
#NLP-Document-Metrics

---
# What is Cosine Similarity
Cosine similarity is a metric which tells how similar a document is to another.
- Requires BOTH documents be in a document vector representation.

Cosine similarity is a good measurement of similarity as...
1) It ignores magnitude.
	- Cosine similarity measures orientation, not magnitude. It is not impacted by frequencies of words, just what words are present.
2) The comparison is normalised.
	- Both vectors are normalised by the product of their magnitude. Therefore, cosine similarity is scale-invariant (scale constant).
3) Computational efficiency.

For 2 document vectors, $\vec{d}_1, \vec{d}_2$, the cosine similarity can be computed via...
$$
cosim(\vec{d}_1, \vec{d}_2) = \frac{\vec{d_1}\cdot \vec{d}_2}{||\vec{d}_1|| ||\vec{d}_2||}
$$

# Interpreting Cosine Similarity.
Cosine similarity is simply the cosine of the angle between two vectors.

$$
cos(\theta) = cosim(\vec{d}_1, \vec{d}_2)
$$
$$
\theta = cos^{-1}(cosim(\vec{d}_1, \vec{d}_2))
$$