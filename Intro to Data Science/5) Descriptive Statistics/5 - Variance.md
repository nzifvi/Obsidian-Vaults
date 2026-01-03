[[3 - Sample Mean]] <- Back
[[4 - Expected Value]] <- Back

---
# What is Variance?
Variance is a statistical measure of how much the outcomes of a sample are spread/dispersed about the expected value.

$$
VAR(X(\omega)) = \frac{1}{|X(\omega)|}\sum_{i = 0}^{|X(\omega)|}\biggr[(\omega_{i} - \bar{x})^{2}\biggr]
$$


# Proof: $VAR[cX(\omega)] = c^2VAR[X(\omega)]$
$$
VAR[cX(\omega)] = \frac{1}{|X(\omega)|}\sum_{i = 0}^{|X(\omega)|}\biggr[(c(\omega_{i} - \bar{x}]))^{2}\biggr]
$$
$$
VAR[cX(\omega)] = \frac{1}{|X(\omega)|}(c^2(\omega_0 - \bar{x})^2 + c^2(\omega_1-\bar{x})^2 +...+c^2(\omega_{|X(\omega)|}-\bar{x})^2)
$$
$$
VAR[cX(\omega)] = c^2\biggr(\frac{1}{|X(\omega)|}((\omega_{0}-\bar{x})^2 + (\omega_1-\bar{x})^2+...+(\omega_{|X(\omega)|}-\bar{x})^2)\biggr)
$$
$$
VAR[cX(\omega)] = c^2VAR[X(\omega)] 
$$
Q.E.D.

# Reason why Variance is Squared
Variance is a squared metric due to the fact that it is possible that, within a sample $S$, two values which have the same absolute value can appear.

Let S equal...
$$
S = \{-1, 1\}
$$
$$
\bar{s} = \frac{1}{2}(-1+1) = \frac{-1+1}{2} = 0
$$
-  Mean of 0 is fine.
- However, when calculating the variance without squaring the terms of the sum, an issue occurs.


$$
VAR(S) = \frac{1}{2}((-1-0) + (1-0)) = \frac{-1+1}{2} = \frac{0}{2}
$$
- Without squaring the terms of the sum, if an outcome is just the negative of another, they will cancel each other out.
- This means the variance would not be truly representative, hence the terms of the sum are always squared to prevent this from happening.