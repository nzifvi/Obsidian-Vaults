[[2 - Learning with Logistic Regression]] $\leftarrow$ Next

---
# What is Logistic Regression?
Linear regression, given a set of input variables, predicts a continuous value. Logistic regression, given a set of input variables, predicts the probability that something belongs to a class.
- Logistic regression is used for binary classification problems.

Logistic regression, as it solves binary classification, attempts to predict the probability of something being a positive class.
$$
y_{actual}=\begin{cases}1\text{ (positive class)}\\0\text{ (negative class)}\end{cases}
$$
- $y_{predicted}$ is the probability of the input belonging to the positive class.
$$
y_{predicted}=P(\text{positive class}| \vec{x})
$$
# Mathematics for Logistic Regression
$$
\vec{\theta}=\begin{bmatrix}\theta_0\\...\\\theta_n\end{bmatrix}, \vec{x}=\begin{bmatrix}1\\x_1\\...\\x_n\end{bmatrix}
$$

$$
z(\vec{\theta}, \vec{x}) = \vec{\theta} \cdot \vec{x} \Rightarrow z(\vec{\theta}, \vec{x}) = \theta_0 +\theta_1x_1 + \theta_2x_2+...+\theta_nx_n
$$
$$
\sigma\biggr(z(\vec{\theta}, \vec{x})\biggr)=\frac{1}{1+e^{-z(\vec{\theta}, \vec{x})}}
$$
$$
y_{actual}= \sigma\biggr(z(\vec{\theta}, \vec{x})\biggr)
$$
Calculating errors, $\mathcal{L(\vec{x}, y_{actual})}$, for logistic regression is done using cross-entropy:
$$
\mathcal{L(\vec{x}, y_{actual})}= \biggr(y_{actual}log(y_{predicted}+(1-y_{actual})log(1-y_{predicted})\biggr)
$$
The global error, $\mathcal{L}$, is calculated with...
$$
\mathcal{L} = \frac{1}{n}\sum_{i=1}^{n}\biggr[\mathcal{L}(\vec{x}_i, y_{actual_i})\biggr]
$$
