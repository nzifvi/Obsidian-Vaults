[[2 - Population, Sample]] <- Back
[[4 - Expected Value]] <- Next

---
# What is the Sample Mean?
The sample mean is the average value in a sample.
- If sample is denoted as X, the sample mean of X is denoted as $\bar{x}$


$$
\bar{x} = \frac{1}{|X|}\sum_{x\in X}[x]
$$

```python
def calculateMean(list) -> float:
	sum = 0.0
	for i in range(len(list)):
		sum += list[i]
	return sum / len(list)

sample = [1, 2, 3, 4, 5, 6, 9, 10, 11]
print(calculateMean(sample))
```
