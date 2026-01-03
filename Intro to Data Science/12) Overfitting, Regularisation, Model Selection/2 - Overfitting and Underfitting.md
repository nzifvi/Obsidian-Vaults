[[1 - Bias and Variance]] $\leftarrow$ Back

---
# 1) What is Overfitting?
Overfitting occurs when a model learns too much from the data it was trained on, including irrelevant details such as noise and outliers.
- Model will work great only on training data that it was trained on. When it encounters new data it will perform poorly.

## 1.1) Overfitting Causes
Some causes of overfitting are:
1) High variance and low bias [[1 - Bias and Variance]].
2) Model is too complex.
3) Size of training data is too small. Model must be trained on more data.

# 2) What is Underfitting?
Underfitting occurs when a model is too simple to capture the details of what is going on in data.
- Model will not work on either training data or new, unseen data.
## 2.1) Underfitting Causes
Some causes of underfitting are:
1) Model is too simple. It may not be able to represent certain parts of the data. Higher dimensions for example.
	- A model for 1st order polynomial would be too simple if it tried to model a 3rd order polynomial. It cannot capture the curve.

