[[1 - What is sklearn]] $\leftarrow$ Back
[[3 - sklearn model evaluation]] $\leftarrow$ Next

#sklearn #MachineLearning #sklearn-training

---
# 1) Training with `sklearn`


```python
import sklearn

model = # some sklearn model object

x = # a sklearn compatible datatype representing the inputs of the model.
yActual = #an sklearn compatible datatype representing corresponding outputs

model.fit(x, yActuals)

```


## Input Data: x
The input data, x, will often be a two dimensional structure where the rows are the data points and each column represents a feature of the data.

Compatible datatypes are...
1) numpy arrays.
2) pandas DataFrames
3) python lists (less common)#
4) SciPy sparse matrices
	- Common for text/TF-IDF vectors.
## Labels: yActual
The labels, yActual, are a one-dimensional structure where each element represents the expected output of a model for a corresponding data point.

Common datatypes are...
1) numpy array.
2) pandas series.
3) python lists.