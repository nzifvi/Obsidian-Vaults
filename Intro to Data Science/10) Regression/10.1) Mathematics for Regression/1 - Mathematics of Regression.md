
---
# 1) Functions part of Linear Regression Process

The parameters vector is $\vec{\theta}$
$$
\vec{\theta}_{1Xm} = [\theta_0, \theta_1,..., \theta_{m-1}]
$$
The inputs vector, representing the domain, is $\vec{x}$
$$
\vec{x} = [x_1, x_2,...,x_n]^T
$$
Linear regression can be performed with an approximating function that is...
1) A polynomial function.
2) Linear combination.

## $f(x)$ is the TARGET FUNCTION
- A sample which has an input as the domain of x and a co-domain $f(x)$.
- Used to iteratively improve the approximating function such that it approaches the target function $f(x)$.


## $g(x; \vec{\theta})$ is the APPROXIMATING FUNCTION
- $g(x;\vec{\theta})$ will be adapted over multiple iterations to better approximate the target function $f(x)$.
- With linear regression, $g(x)$ will be a linear equation.
$$
g(x;\theta)=\theta x+\epsilon
$$

## $L(x_i;\theta,\vec{x})$ is the LOSS function.
- Loss function is an error measure for a single output of the approximating function.
- Measures how difference between actual output of approximating function versus expected output from the target function.
$$
L(i;\vec{\theta}, \vec{x}) = \biggr(g(x_{i};\vec{\theta})-f(x_i)\biggr)^2
$$

- The input of the loss function is a residual $\epsilon$
	- Residuals are the difference between the approximating function versus the target function for a given input $x_i$.

Loss function can be rewritten as...
$$
\epsilon_1 = g(x_{i}; \vec{\theta})- f(x_i) \Rightarrow L(\epsilon_i)=\epsilon_{1}^{2}
$$
The goal of regression is to minimise the residuals over multiple iterations.


## $J(\theta)$ is the OBJECTIVE function.
- Provides a GLOBAL ERROR with respect to the set of parameters $\vec{\theta}$ which then is used to update the approximating function so that it better approximates target function.
- Used to measure how different an approximating function is, based on it's parameters $\vec{\theta}$, from the target function.
$$
J(\theta)=\frac{1}{n}\sum_{i=1}^{n}\biggr[L(i;\theta, \vec{x})\biggr]
$$

$\frac{dJ(\theta)}{d\theta}$ is the objective function derivative.
- It forms a multivariable derivative since $\vec{\theta}$ is a vector of the approximating function's parameters. 

# 2) Modelling with Polynomial Function
$$
g(x; \vec{\theta}) = \theta_{m-1}x^{m-1}+...+\theta_0x^0
$$
$$
\theta_0x^0 = \theta_0
$$
$$
g(x; \vec{\theta}) = \theta_{m-1}x^{m-1}+...+\theta_0
$$
- m the size of the parameters vector determines how many terms there will be polynomial approximating function.

## 2.1) Updating Approximating Polynomial Function
$$
g(x; \vec{\theta}) = \theta_{m-1}x^{m-1}+...+\theta_0
$$

Loss Function
$$
L(x_i;\vec{\theta}) = (g(x_i;\vec{\theta}) - f(x_i))^2
$$

Objective Function
$$
J(\vec{\theta})=\frac{1}{n}\sum_{i=0}^{m-1}\biggr[L(x_i;\vec{\theta})\biggr]
$$
Nabla of Objective Function
$$
\nabla J(\vec{\theta}) = \biggr[\frac{\partial J(\vec{\theta})}{\partial \theta_0}, \frac{\partial J(\vec{\theta})}{\partial \theta_1},...,\frac{\partial J(\vec{\theta})}{\partial \theta_{m-1}} \biggr]^T
$$
$$
\frac{\partial J(\vec{\theta})}{\partial \theta_j} = \frac{\partial}{\partial\theta_j}\biggr[\frac{1}{m}\sum_{i=0}^{m-1}\biggr[L(x_i;\vec{\theta})\biggr]\biggr]=\frac{1}{m}\sum_{i=0}^{m-1}\biggr[\frac{\partial}{\partial \theta_j}\biggr[L(x_i; \vec{\theta})\biggr]\biggr]
$$
$$
\frac{\partial}{\partial \theta_j}\biggr[L(x_i; \vec{\theta})\biggr] = \frac{\partial}{\partial\theta_j}\biggr[(g(x_i;\vec{\theta}) - f(x_i))^2\biggr]
$$
$$
a = g(x_i;\vec{\theta}) - f(x_i)
$$
$$
a = g(x_i;\vec{\theta}) - f(x_i) \Rightarrow L(x_i;\vec{\theta}) = a^2
$$
$$
\frac{\partial J(\vec{\theta})}{\partial \theta_j}=\frac{\partial J(\vec{\theta})}{\partial a} \cdot \frac{\partial a}{\partial \theta_j}
$$
$$
\frac{\partial J(\vec{\theta})}{\partial a} \cdot \frac{\partial a}{\partial \theta_j}=\frac{\partial}{\partial a}\biggr[a^2\biggr]\cdot \frac{\partial}{\partial \theta_j}\biggr[g(x_i;\vec{\theta}) - f(x_i)\biggr]
$$$$
\frac{\partial}{\partial a}\biggr[a^2\biggr]=2a
$$
$$
\frac{\partial J(\vec{\theta})}{\partial \theta_j}=2(g(x_i;\vec{\theta}) - f(x_i))\frac{\partial}{\partial \theta_j}\biggr[g(x_i;\vec{\theta}) - f(x_i)\biggr]
$$

# 3) Modelling with a Linear Combination
