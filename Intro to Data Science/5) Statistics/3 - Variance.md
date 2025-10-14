[[2 - Expected Value]] <- Back

---
# What is Variance?
Variance is a statistical measure of how much the outcomes of a sample are spread/dispersed about the expected value.

$$
VAR[X(\omega)] = \frac{1}{|X(\omega)|}\sum_{i = 0}^{|X(\omega)|}\biggr[(\omega_{i} - E[X(\omega)])^{2}\biggr]
$$


# Proof: $VAR[cX(\omega)] = c^2VAR[X(\omega)]$
$$
VAR[cX(\omega)] = \frac{1}{|X(\omega)|}\sum_{i = 0}^{|X(\omega)|}\biggr[(c(\omega_{i} - E[X(\omega)]))^{2}\biggr]
$$
$$
VAR[cX(\omega)] = \frac{1}{|X(\omega)|}(c^2(\omega_0 - E[X(\omega)])^2 + c^2(\omega_1-E[X(\omega)])^2 +...+c^2(\omega_{|X(\omega)|}-E[X(\omega)])^2)
$$
$$
VAR[cX(\omega)] = c^2\biggr(\frac{1}{|X(\omega)}((\omega_{0}-E[X])^2 + (\omega_1-E[X(\omega)^2+...+(\omega_{|X(\omega)|}-E[X(\omega)])^2)\biggr)
$$
$$
VAR[cX(\omega)] = c^2VAR[X(\omega)] 
$$
Q.E.D.

# Reason why Variance is Squared
Variance is a squared metric