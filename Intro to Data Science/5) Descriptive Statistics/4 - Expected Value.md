[[3 - Sample Mean]] <- Back
[[5 - Variance]] <- Next

---
# What is an Expected Value?
An expected value of a sample, $E[X]$, is the average value were a sample to be taken many times.
- Sum of an outcome multiplied by the probability of an experiment being that outcome.
$$
E[X] = \sum_{i=0}^{X}\biggr[P(X=x_i)\cdot x_i\biggr]
$$

# Linearity of Expected Value
Expected value's have the law of linearity applicable to them. 
- Coefficients of the random variable can be factored out to just be coefficients of the expected value.
- The expected value of the sum of n independent random variables can be calculated by taking the sum of their expected values.

$$
E[X(\omega) + Y(\omega)] = E[X(\omega)] + E[Y(\omega)]  
$$
$$
E[aX(\omega)] = aE[X(\omega)]
$$
$$
a,b \in R\hspace{0.2cm}|\hspace{0.2cm}E[aX(\omega) + bY(\omega)] = aE[X(\omega)] + bE[Y(\omega)]  
$$

# Mean vs. Expected Value
The mean is not the same as the expected value.
- Mean $\bar{x}$ is the average value of a sample.
- Expected value, $E[X]$, is the average value most probable to appear based on a probability distribution.