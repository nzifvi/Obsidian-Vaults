[[1,1 - What is Statistical Inference]] <- Back

---
# 1) What are Confidence Intervals?
Confidence intervals are an interval of values where a population statistic may be between.
- Built via sample statistics, as the population statistic can never truly be calculated but only estimated.
- Meaning "I am x% confident that the population statistic lies between point a to point b."

# 2) Building a Confidence Interval
Given a sample statistic, $x$, a confidence interval can be built using it.
- Should always be done for any given sample statistic.

Let the confidence interval of sample statistic $x$ be denoted as...
$$
[a, b]
$$

$$
a = x - (z^* \cdot \sigma)
$$
$$
b = x + (z^* \cdot \sigma)
$$
Where...
- $z^*$ is the critical value.
	- $z^*$ depends on...
		1) Desired confidence level.
		2) Distribution being used.
- $\sigma$ is the standard deviation of the sample.