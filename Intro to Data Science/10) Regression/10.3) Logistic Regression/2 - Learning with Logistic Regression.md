[[1 - About Logistic Regression]] $\leftarrow$ Back 

---
# Recap: calculating local and global loss with Logistic Regression
Calculating errors, $\mathcal{L(\vec{x}, y_{actual})}$, for logistic regression is done using cross-entropy:
$$
\mathcal{L(\vec{x}, y_{actual})}= -\biggr(y_{actual}log(y_{predicted})+(1-y_{actual})log(1-y_{predicted})\biggr)
$$
The global error, $\mathcal{L}$, is calculated with...
$$
\mathcal{L} = \frac{1}{n}\sum_{i=1}^{n}\biggr[\mathcal{L}(\vec{x}_i, y_{actual_i})\biggr]
$$
$$
\nabla \mathcal{L} = \begin{bmatrix}
\frac{\delta \mathcal{L(\vec{x}, y_{actual})}}{\delta \theta_1}
\\ ...
\\ \frac{\delta \mathcal{L(\vec{x}, y_{actual})}}{\delta \theta_n}
\end{bmatrix}
$$
Where...
$$
\frac{\delta \mathcal{L}}{\delta \theta_j} = (y_{predicated}-y_{actual})x_j
$$
# Updating Weights in Logistic Regression Model
Each weight, $\theta \in \vec{\theta}$, is updated using gradient descent:
$$
\theta_j \leftarrow \theta_j - \alpha \frac{\delta \mathcal{L}}{\delta \theta_j}
$$