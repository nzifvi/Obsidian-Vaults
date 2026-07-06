[[1,1 - Gaussian Distribution]] $\leftarrow$ Back

---
# Why Normalise?
Normalisation is done as models can easily be lead astray by the scale of vector's rectangular components.
- Normalising vectors makes certain algorithms increasingly optimised.

In any...
1) Distance based algorithm: normalisation is crucial.
2) Gradient based algorithm: normalisation is recommended, makes gradient descent faster.
3) PCA (dimensionality reduction): normalisation is crucial.
# L1 Normalisation
L1 normalisation is best for sparse data. It is not as sensitive to outliers as L2 normalisation.
- aka Manhattan Distance
- It can result in many elements being, or being near, zero.
$$
||\vec{v}||_1 = \sum_{i=1}^n\biggr[|x_i|\biggr]
$$
$$
\hat{v}=\frac{\vec{v}}{||\vec{v}||_1}
$$
# L2 Normalisation
L2 normalisation is best for dense data. However, it is sensitive to outliers which will result in the normalisation still being large.
- aka Euclidian Distance
- All elements post normalisation are preserved: normalisation produces no zero values.
$$
||\vec{v}||_2 = \sqrt{\sum_{i=1}^{n}\biggr[x^2_i\biggr]}
$$
$$
\hat{v}=\frac{\vec{v}}{||\vec{v}||_2}
$$