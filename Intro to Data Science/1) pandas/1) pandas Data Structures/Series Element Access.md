[[Pandas Series]] $\leftarrow$ Back

---
# Accessing Elements of Series

Two function members of Series obj exist to access elements of Series obj...
1) `loc[]`: location
	- used to access an element given it's label.
2) `iloc[]`: integer location
	- used to access an element given an integer position
	- useful for iterating over the Series

```python
import pandas
import random

def populateSample(sampleList, populateTill) -> list:
	for i in range(0, populateTill):
		sampleList.append(random.randrange(1, 100))
		

sampleList = []
populateSample(sampleList, 20)
series = pandas.Series(sampleList)
for i in range(0, len(series)):
	print(series.iloc[i])
```

- `loc[]` works by taking a label which corresponds to an element of the data of the Series obj.

# Filtering
Instead of using a for loop to find values which meet a condition, the condition can be directly applied to Series object via index.
```python
greaterThan50 = series[series > 50]
print(greaterThan50)
```
Accessing a series by a condition returns a temporary Series object.
- Can assign this to a variable


# Vector Math
Operations can be performed to an entire Series object at once.
- Much faster than doing it via a loop in python, pandas is implemented directly in C so it is therefore much faster.

```python
adjustedSeries = series + 1000000
print(adjustedSeries)
```

