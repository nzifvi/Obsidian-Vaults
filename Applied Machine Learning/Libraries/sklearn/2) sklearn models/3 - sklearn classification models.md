[[2 - sklearn regression models]] $\leftarrow$ Back
[[4 - Creating custom Models]] $\leftarrow$ Next

#skleark #sklearn-classification-models #sklearn-models

---
# Types of `sklearn` Classification Models
`sklearn` provides many classification models.

Some, but not all, are...
1) LogisticRegression
2) Perceptron
3) Naive Bayes Classifiers
4) Ensemble Methods

# 1) LogisticRegression
`LogisticRegression` model is a class part of the `sklearn.linear_model` sub-library.

```python
model = sklearn.linear_model.LogisticRegression(
	penalty,
	C,
	solver,
	max_iter
)
```

Penalty defines the regularisation type used to prevent overfitting.
$$
penalty \in \biggr\{l1, l2, elasticnet, None\biggr\}
$$
- Default value is l2.

C defines the inverse regularisation strength.
- Default value is 1.0
- C is basically a measurement of how much the training data is trusted vs how much it prefers simple solutions.
- As C $\rightarrow \infty$, model tries harder to classify every training example correctly. 
	- Larger C = more trust in training data set.
	- ONLY increase C a lot if training data is trusted.
	- Large C risks overfitting.
- As $C \rightarrow 0$, model prefers a simpler and smoother decision boundary.
	- Smaller C = less trust in training data set.
	- Small C risks underfitting.

solver defines the optimisation algorithm used to adjust the weights of the logistic regression model.
$$
solver \in \bigg\{\text{lbfgs}, \text{liblinear}, \text{sag}, \text{newton-cg}\bigg\}
$$
- default is lbfgs.
- NOTE: certain optimisation algorithms cannot be used with certain regularisations. Always check the combination is valid.

max_iter is a parameter which controls the maximum number of iterations the selected optimisation algorithm is ran for.

# 2) Perceptron

# 3) Naive Bayes Classifiers

# 4) Ensemble Methods