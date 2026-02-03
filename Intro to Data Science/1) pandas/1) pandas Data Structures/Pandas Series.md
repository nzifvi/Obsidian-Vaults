
---
# What is a Pandas Series?
A pandas series is a one dimensional labelled array.

A series has...
1) An index: a label, which acts as a key, to uniquely identify elements in the series.
	- Acts as an address for that Series.
	- A list can be a numeric value, a string, or a datetime (for time series analysis).
2) Values: the data of the series.

By default, if no labels are provided when initialising Series object, labels will be numeric indices starting from 0.

# Creating a Series

```python
import pandas as pd
sample = [100, 250, 400]

# Series with default indices

series = pd.Series(data=sample)

print(series)

# Series with custom indices
labels = ["element1", "element2", "element3"]
series2 = pd.Series(data=sample, index=labels) # let list of custom labels = index
print(series2)
```

## Customising a Series object in Initialisation
Series() constructor has 4 common arguments that allow for the Series object to be customised:
1) data
	- list, dictionary, or array containing data to load into Series obj.
2) index
	- a list of labels to assign to elements of the array
	- index\[i\] will become label for data\[i\]
3) dtype
	- forces a specific datatype for the elements of the data in Series
4) name
	- gives the Series obj a name, which uniquely identifies it if later added to a DataFrame obj.
