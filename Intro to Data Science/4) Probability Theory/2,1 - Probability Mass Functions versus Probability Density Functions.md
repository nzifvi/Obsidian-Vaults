
---
# What is a Probability Mass Function?
A probability mass function assigns a probability to an outcome of a discrete random variable.
- Random variables must be discrete in order to have a probability mass function.

For PMFs...
$$
x\in X | f_{X}(x) = P(X=x)
$$
# What is a Probability Density Function?
A probability density function specifies the probability that an outcome of a continuous random variable falls within a bound.
- If a random variable is continuous, it will have a PDF which must be integrated to get the PMF to determine probabilities of outcomes.

A PDF is the probability per unit length.
- Measure of how "dense" the probability of something occurring is about a point.

For PDFs...
$$
x\in X | f_{X}(x) \cancel{=} P(X=x)
$$
$\int f_X(x)dx$ is the PMF of a PDF.
$$
\int_{a}^{b}[f_{X}(x)]dx = P(a \leq X \leq b)
$$
$$
x\in X | \int_{- \infty}^{x}[f_{X}(x)]dx = P(X=x)
$$