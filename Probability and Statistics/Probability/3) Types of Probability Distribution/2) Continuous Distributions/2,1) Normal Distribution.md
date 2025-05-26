[[1) What makes a Distribution a Continuous one]] <- Back

---
## What is a Normal Distribution?
A Normal Distribution is a type of Distribution that models probability density over a continuous variable.

Probability density = how probable values, around a point x, are to occur.
- High probability density near a point = more probable that values will occur around that point x.
- Low probability density near a point = less probable that values will occur around that point x.

- f(x = 5) $\neq$ P(X = 5)
	- Does not give you the probability of x being 5...
- f(x = 5) = PDF(5)
	- PDF(x = 5) tells you how probable values around 5 are.

A Normal Distribution itself does not give the probability of something being that value.
- To get that, you must integrate the probability density function over an interval.

Normal Distribution aka Gaussian Distribution
- The Probability Density Function required to produce Gaussian Distribution.

## Probability Density Function

$$
f(x) = \frac{1}{\sigma \cdot \sqrt{2\pi}}e^{-\frac{1}{2}\biggr( \frac{x-\mu}{\sigma}\biggr)^2}
$$

x is the continuous random variable.
$\mu$ is the mean.
$\sigma$ is the standard deviation.
$\sigma^{2}$ is the variance.

All must be produced from a data set.
[[2,2) Producing Required Constants of Probability Density Function]]

## Meaning of PDF's constants

#### 1) Mean $\mu$
$\mu$, the mean, is the mean of the Gaussian Distribution.
- The value of $\mu$ is the expected value of the continuous random variable the Gaussian Distribution models.

- $\mu$ is also the x-ordinate for the bell curve's, produced by the PDF, axis of symmetry. 
	- Any values of x < $\mu$ are less probable to exist.
	- Any values of x > $\mu$ are less probable to exist.

![[Pasted image 20250421113606.png]]

- $\mu$ is ALSO the absolute maxima of the bell curve. It is also the turning point of the bell curve.
	- PDF values will begin to decrease for any x > $\mu$

#### 2) Standard Deviation $\sigma$

$\sigma$, the standard deviation, controls the width of the bell curve.
- Consequently, $\sigma$ controls the probability density for all values x.

![[Pasted image 20250421113840.png]]

- As $\sigma$ -> $\infty$, the probability density for all possible outcomes x becomes more probable.

- As $\sigma$ -> $0$, the probability density for all possible outcomes x approaches 0.

## Building a Gaussian Distribution

$$
S = [1, 10]
$$
$$
S_1 \in S
$$
Suppose we have the data set, $S_1$, modelling the length of bolts in cm.

$$
S_1= \{ 1, 1, 1, 2, 2, 3, 4, 4, 4, 5, 5, 6, 6, 1, 1, 2, 2, 3, 4, 5, 1, 1, 7, 5, 4, 3, 2\}
$$

A Gaussian distribution can be produced to find the probability density for each possible outcome of a random variable based on $S_1$

$$
X\in\{1, 2, 3, 4, 5, 6, 7\}
$$
$$
f(x) = \frac{1}{\sigma \cdot \sqrt{2\pi}}e^{-\frac{1}{2}\biggr( \frac{x-\mu}{\sigma}\biggr)^2}
$$
Using the data set, S, solve the constants of the PDF.

$\mu = 3.5$
$\sigma^2 = 3.24$
$\sigma = 1.8$

$$
f(x) = \frac{1}{1.8 \cdot \sqrt{2\pi}}e^{-\frac{1}{2}\biggr( \frac{x-3.5}{1.8}\biggr)^2}
$$
Now a Gaussian Distribution, $X~N(\mu, \sigma^2)$, can be produced using the PDF now that the constants have been solved for.

Now, specific questions can be asked... such as:
"What is the probability density that I will get a bolt around 5cm?"

f(5) = 0.1566
- Compared to other possible values, the probability of getting a 5cm bolt is 0.1566"
- To get the probability of actually getting a 5cm bolt, integration is required.


## Best ways to Represent a Gaussian Distribution
If getting specific values, just use f(x) where x equals some value.

If wanting to show the bell curve, use a graph. Tables cannot be continuous so they cannot fully represent the possible range of values x.
### Graphs





