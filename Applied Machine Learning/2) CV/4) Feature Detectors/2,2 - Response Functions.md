[[2,1 - Scaling]] $\leftarrow$ Back
[[3,1 - Feature Descriptors]] $\leftarrow$ Next

---
# Response Functions
Response functions are used to determine

# Laplacian of Gaussian
The Laplacian of Gaussian acts as a blob detector.

The Laplacian of gaussians can be approximated by a difference of Gaussians.
- Difference of Gaussians is more efficient to implement than the Laplacian.
$$
\mathcal{L}=\sigma^2\biggr(\mathcal{N}_1(x,y, \sigma) + \mathcal{N}_2(x,y,\sigma)\biggr)
$$
$$
\Delta \mathcal{N}=\mathcal{N}_i(x,y,k\sigma)-\mathcal{N}_j(x,y,k\sigma)
$$
$$
\Delta \mathcal{N} \approx \mathcal{L}
$$

