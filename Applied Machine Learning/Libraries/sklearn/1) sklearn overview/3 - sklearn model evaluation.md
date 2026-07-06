[[2 - sklearn model training]]

#sklearn #sklearn-evaluation

---
# 1) `sklearn` Classification Model Evaluation
`sklearn.metrics` sub-library provides multiple classes used to evaluate the classification performance of `sklearn` classification models .
- MUST have labelled test data.

These performance evaluating classes are...
1) `sklearn.metrics.accuracy_score()`
	- Measures how accurate a model is at predicting true positives and negatives.
2) `sklearn.metrics.classification_report()`
	- Displays metrics such as accuracy, precision, recall, and F1 score.
3) `sklearn.metrics.confusion_matrix()`
	- Displays a confusion matrix from a model.

ALL classification models require...
- Test data.
- Corresponding test data labels
... as parameters on call.




