[[8 - Z-score]] $\leftarrow$ Back
[[10 - Correlation]] $\leftarrow$ Next

---
# What is Covariance?
Covariance is a measure of how two variables change together.
$$
Cov(X,Y)
$$
If...
- $Cov(X,Y) > 0$, positive covariance, then the two random variables increase/decrease together.
- $Cov(X,Y) < 0$, negative covariance, one random variable increases whilst the other decreases.
- $Cov(X,Y) = 0$, no covariance, no consistent linear relationship exists between the random variables.

$$
Cov(X,Y)= \frac{1}{n-1}\sum_{i=1}^{n}\biggr[(x_i - \bar{x})(y_i -\bar{y})\biggr]
$$
- n-1 = DOF of the samples.
- $\bar{X}$ mean of random variable $X$.

# Python Implementation

```python
import random
import matplotlib.pyplot as plt
import pandas

def generateRandomSeries(sampleSize:int) -> pandas.Series:
	elements = []
	for i in range(0, sampleSize):
		elements.append(random.randrange(1, 100))
	return pandas.Series(elements)

def calculateCovariance(series1:pandas.Series, series2:pandas.Series) -> float:
	series1Mean = series1.mean()
	series2Mean = series2.mean()
	sumOfTerms = 0.0
	for i in range(len(series1)):
		sumOfTerms += (series1[i]-series1Mean)*(series2[i]-series2Mean)
	return (1/(len(series1) + len(series2) - 2)) * sumOfTerms

series1 = generateRandomSeries(100)
series2 = generateRandomSeries(100)
print(calculateCovariance(series1, series2))
plt.scatter(series1, series2, alpha=0.5)
plt.xlabel("series1")
plt.ylabel("series2")
plt.grid(True)
plt.show()
```
