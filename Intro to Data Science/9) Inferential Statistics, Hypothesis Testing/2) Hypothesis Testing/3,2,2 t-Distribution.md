[[3,2,1 t-Test]] $\leftarrow$ Back

---
# What is the t-Distribution?
A t-Distribution is a PDF which is similar to the Gaussian distribution.
- It has heavier tails though.

t-Distributions are often more safe and effective than Gaussian distributions as...
1) A Gaussian distribution is only accurate when you have incredibly large amounts of samples from a population, essentially turning it into the population.

Any t-score will be a point on a t-distribution
# t-Distribution Formula

$$
f(t, v)=\frac{\Gamma\biggr(\frac{v+1}{2}\biggr)}{\sqrt{\pi v}\Gamma\biggr(\frac{v}{2}\biggr)}\biggr(1+\frac{t^2}{v}\biggr)^{-\frac{v+1}{2}}
$$
- $t$: t-score
	- can be  a specific value, a t-score calculated from a sample
		OR
	- a range, $[a, b] | b > a$, to graph the t-Distribution

- $v$: degrees of freedom
	- The degrees of freedom of a sample.

- $\Gamma()$ is the gamma function
	- Allows the factorial of real numbers, not just integer values, to be computed

$$
\Gamma(z)=\int^\infty_0\biggr[x^{z-1}e^{-x}\biggr]dx
$$

Python `scpipy` library has a gamma function which allows real number factorials to be computed
```python
from scipy.special import gamma
print(gamma(2.5))
```

To calculate DOF, $v$, it depends on the t-test the t-score came from:
1) ONE-SAMPLE T-TEST
$$
v=|X|-1
$$
2) STUDENT'S T-TEST
$$
v = |X_1| + |X_2| - 2
$$
3) WELCH'S T-TEST

# t-Distribution in Python
```python
# done with one sample t-test producing t-score
import seaborn
from scipy.special import gamma
import pandas
import numpy
import random # used for rand no. generation to create a sample
import matplotlib.pyplot as plt

def generateSample(populateTill) -> list:
	sampleList = []
	for i in range(0, populateTill):
		sampleList.append(random.randrange(1, 100))
	return sampleList

def calculateOneSampleTScore(series : pandas.Series, benchmarkMean : float) -> float:
	return (series.mean() - benchmarkMean) / (series.std() / numpy.sqrt(len(series)))

def tDistributionFunction(tScore : numpy.ndarray, dof : int) -> numpy.ndarray:
	numerator = gamma((dof + 1)/2)
	denominator = numpy.sqrt(numpy.pi * dof) * gamma(dof/2)
	return (numerator/denominator)*(1+(tScore**2 / dof))**(-(dof+1)/2)

series = pandas.Series(generateSample(100))
xOrdinates = numpy.linspace(-10, 10, 1000)
dof = len(series) - 1
tDistribution = tDistributionFunction(xOrdinates, 50)
tScore = calculateOneSampleTScore(series, 50)
plt.plot(xOrdinates, tDistribution, label=f't-dist (df={dof})')
plt.axvline(tScore, color='red')
plt.fill_between(xOrdinates, tDistribution, alpha=0.1)
plt.legend()
plt.show()
```

# Hypothesis Testing with t-Distribution
To convert a t-Score, $t$, into a p-value, $p$, must integrate the t-Distribution:
- Depending if it is a one or two tailed test

## 1 Tailed Test
To do a right tail test (sample mean 1 is greater than sample mean 2), do...

$$
p = \int_t^\infty\biggr[f(x, v)\biggr]dx
$$
To do a left tail test (sample mean 1 is less than sample mean 2), do...
$$
p=\int_{-\infty}^t\biggr[f(x,v)\biggr]dx
$$
## 2 Tailed Test
$$
p = 2\int_{|t|}^\infty\biggr[f(x, v)\biggr]dx
$$
In python, this is easy:
- uses sf function from scipy instead of 1 - cdf. This is due to cdf causing floating-point precision loss
```python
from scipy import stats
pOneTailed = stats.t.sf(abs(tScore), df=dof) # one tailed
print(pOneTailed)
pTwoTailed = 2 * stats.t.sf(abs(tScore), df=dof) # two tailed
```
