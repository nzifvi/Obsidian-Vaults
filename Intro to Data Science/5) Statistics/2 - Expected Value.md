[[1 - Population, Sample]] <- Back
[[3 - Variance]] <- Next

---
# What is the Expected Value?
The expected value, aka mean, is the most probable value to appear from a given random variable.
- Denoted as $E[X(\omega)]$

$$
E[X(\omega)] = \frac{1}{|X(\omega)|}\sum_{i = 0}^{|X(\omega)|}\biggr[\omega_{i}\biggr]
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
