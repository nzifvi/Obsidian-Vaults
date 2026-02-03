[[3,1 - Types of Hypothesis Tests]] <- Back

---
# What is the t-Test
Student's t-test is a statistical method used to determine if there is a significant difference between the means of two samples, or a given benchmark value.

A...
- High t-score, $t$ indicates that there is a difference between the mean of two samples.
- Low t-score, $t$, indicates that there is not much of a difference between the mean of two samples.
	- OR there are massive varying values in the samples: reducing the effectivity of the t-test (MUST BE FIXED)


NOTE: t-scores CANNOT be directly used for hypothesis testing, additional steps required.

# Types of t-Test

## One-Sample t-Test
One Sample t-Test is used to produce a t-score which measures the difference between a sample's mean and a benchmark value $\mu$

1) Data within sample MUST be independent.
2) Data of sample should be approximately Gaussian distributed

$$
t=\frac{\bar{x}- \mu}{\frac{\sigma}{\sqrt{|X|}}}
$$
## Student's t-Test
Student's t-Test is used to produce a t-score which measures the difference between two sample's means

TEST REQUIREMENTS:
1) Data within sample MUST be independent.
2) Samples must be independent: should NOT influence each other.
3) Data should be approximately Gaussian distributed.
4) The standard deviation between groups should be approximately equal.

$$
t=\frac{\bar{x_1}-\bar{x_2}}{\sqrt{\frac{\sigma_1^2}{|X_1|}+\frac{\sigma_2^2}{|X_2|}}}
$$

## Welch's t-Test
# Example of producing t-Score

```python
import random
import pandas
import numpy
import seaborn
import matplotlib.pyplot as plt

import pandas
import random

def generateSample(populateTill) -> list:
	sampleList = []
	for i in range(0, populateTill):
		sampleList.append(random.randrange(1, 100))
	return sampleList
	
sample1 = pandas.Series(generateSample(100))
sample2 = pandas.Series(generateSample(100))

tScore = (sample1.mean() - sample2.mean()) / (numpy.sqrt((sample1.std()**2) / len(sample1)) + ((sample2.std()**2) / len(sample1)))
print(tScore)

dataFrame = pandas.DataFrame({
	'Value': pandas.concat([sample1, sample2]),
	'Group': ['Sample 1']*len(sample1) + ['Sample 2']*len(sample2)
})

plt.figure(figsize=(8, 6))
seaborn.stripplot(x = 'Group', y = 'Value', data = dataFrame, jitter=True, alpha = 0.6)
plt.show()
```

# How to Hypothesis Test via t-Test
A t-score alone cannot be used to hypothesis test.
- It is a metric which measures difference between the means of a sample.

To hypothesis test, the t-distribution is required
- [[3,2,2 t-Distribution]]

