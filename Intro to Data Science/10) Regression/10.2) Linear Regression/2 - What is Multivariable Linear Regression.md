[[1,1 - What is Monovariable Linear Regression]] <- Back

---
# 1) What is Multivariable Linear Regression?
Multivariable linear regression is the same idea as monovariable linear regression except rather than the sample being 2 dimensional, it is nth dimension such that n > 2.

This requires...
1) Approximating function to be a linear combination of features. Each feature is it's own random variable with outcomes.

For example, to model...

| Height | Age | BPM |
| ------ | --- | --- |
| ...    | ... | ... |
| ...    | ... | ... |
| ...    | ... | ... |
You use a linear combination with 3 inputs:
$$
g(x_1, x_2; \vec{\theta})
$$
Where...
- Each input is a member of a given random variable of the sample.
	- $x_1 \in$ Height
	- $x_2 \in$ Age
	- $x_0$ is the dummy variable, let it always equal 1.

- For each random variable, you have a weight which is a coefficient of the input arguments.

$$
g(x_1, x_2; \vec{\theta}) = \theta_1x_1 + \theta_2x_2 + \theta_0 \cdot 1
$$
$$
g(x_1, x_2; \vec{\theta}) = \theta_1x_1 + \theta_2x_2 + \theta_0
$$
The approximating function in it's linear algebra form is...
$$
\begin{bmatrix}  
1 & x_1 & x_2\\   
\end{bmatrix}\begin{bmatrix}  
\theta_0\\  
\theta_1\\
\theta_2
\end{bmatrix}
$$

An entire data sample can be represented by transforming the features vector into a features matrix.
- Each row represents a sample. Each column represents a random variable.

For the sample...

| $f(X_1, X_2)$             | $X_1$       | $X_2$     |
| ------------------------- | ----------- | --------- |
| $f(x_{1_{1}}, x_{2_{1}})$ | $x_{1_{1}}$ | $x_{2_1}$ |
| $f(x_{1_{2}}, x_{2_{2}})$ | $x_{1_2}$   | $x_{2_2}$ |
| $f(x_{1_{3}}, x_{2_{3}})$ | $x_{1_3}$   | $x_{2_3}$ |
| ...                       | ...         | ...       |
| $f(x_{1_{n}}, x_{2_{n}})$ | $x_{1_n}$   | $x_{1_n}$ |

$$
F=\begin{bmatrix}  
1 & x_{1_{1}} & x_{2_{1}}\\
1 & x_{1_{2}} & x_{2_{2}}\\
1 & x_{1_{3}} & x_{2_{3}}\\
... & ... & ...\\
1 & x_{1_{n}} & x_{2_{n}}
\end{bmatrix}
$$
Consequently, the approximating function becomes a vector when...

$$
F\vec{\theta} = \vec{g(X_1, X_2; \vec{\theta})}
$$

$$
\begin{bmatrix}  
1 & x_{1_{1}} & x_{2_{1}}\\
1 & x_{1_{2}} & x_{2_{2}}\\
1 & x_{1_{3}} & x_{2_{3}}\\
... & ... & ...\\
1 & x_{1_{n}} & x_{2_{n}}
\end{bmatrix}
\begin{bmatrix}  
\theta_0\\  
\theta_1\\
\theta_2
\end{bmatrix}
=
\begin{bmatrix}  
g(x_{1_{1}}, x_{2_{1}}; \vec{\theta})\\  
g(x_{1_{2}}, x_{2_{2}}; \vec{\theta})\\
g(x_{1_{3}}, x_{2_{3}}; \vec{\theta})\\
...\\
g(x_{1_{n}}, x_{2_{n}}; \vec{\theta})
\end{bmatrix}
$$

# 2) Performing Multivariable Linear Regression

Per iteration, to produce the residuals vector $\vec{\epsilon}$, do...
$$
\vec{\epsilon} = \vec{f(x)} - F\vec{\theta}
$$
