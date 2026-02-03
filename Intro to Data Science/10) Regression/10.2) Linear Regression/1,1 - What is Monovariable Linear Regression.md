
---
# 1) What is Linear Regression?
Linear regression = statistical method used to model a relationship between a dependent variable and 1 or more independent variables by fitting a linear equation to a data set.
- Uses a linear equation and approximates a target function via gradient descent.
- The linear combination will approximate a line of best fit through the sample.

For linear regression, the a 1st order polynomial term will be used as the approximating function.
$$
g(x;\vec{\theta}) = \theta_{1}x^1+\theta_0
$$
$$
\vec{\theta}=[\theta_0, \theta_1]
$$

For linear regression, another term is added to the approximating function: $\epsilon$
- $\epsilon$ is the error term.

$$
g(x;\vec{\theta})=\theta_1x+\theta_0+\epsilon
$$

Updating the approximating function works the same as updating a polynomial approximating function (covered in [[1 - Mathematics of Regression]])

# 2) Setting up a Sample for Linear Regression
A sample is used to train the model: done by updating the approximating function over multiple iterations.

For an $n^{th}$ dimension sample, there will be n axes.
- (heartBPM, BMILevel) will result in 2 axes: one per random variable.
	- f(heartBPM) = BMILevel.
	- If n = 2, let it the approximating function be a 1st order polynomial.
- (heartBPM, BMILevel, ageOfDeath) will result in 3 axes.
	- f(heartBPM, BMILevel) = ageOfDeath.
	- If n > 2, let the approximating function be a linear combination.

# 3) Assumptions:

## 3.1) Assumptions for Loss Function:
1) A combination of inputs for the loss function are independent from another combination of inputs.

2) The distribution of the loss function, or the residuals, will be Gaussian.
	- [[1,1 - Gaussian Distribution]] $\leftarrow$ How to check for Gaussian Distributions

3) Residuals should be identically distributed.

