[[5 - Using Predictions to label Unseen Data]] $\leftarrow$ Back
[[6,5,2 - F1-Score]] $\leftarrow$ Related

---
# Evaluating Classifiers
Must know how to evaluate classifiers.
- Important to know how well a classifier will perform on unseen documents.
- Evaluating classifiers allows the best to be chosen for a given scenario.

A labelled data set, not use in training, is required for evaluation.
- Labelled data set comes in (document, class) pairs. Class element denotes the classification of the document.

Evaluations done using the training set.

# Accuracy and Error Rate
For a document, x, it belongs to either set T or F if the prediction of x matches the class label of x.
Let...
$$
T = \{x | prediction(x)=label(x)\}
$$
$$
F = \{x|prediction(x) \cancel{=}label(x)\}
$$
$$
T+F = Documents_{Train}
$$
- D is the entire set of training documents
#### Accuracy
Accuracy is the proportion of documents that are classified correctly out of the total number of training documents.
$$
Accuracy = \frac{|T|}{|Documents_{Train}|}
$$


#### Error Rate
Error Rate is the proportion of documents that are classified incorrectly out of the total number of training documents.
$$
ErrorRate = \frac{|F|}{|Documents_{Train}|}
$$
$$
ErrorRate = 1 - Accuracy 
$$
# Confusion Matrix
Can produce a confusion matrix which further evaluates the classifier.

![[Pasted image 20260207150142.png]]
# Precision and Recall
Precision is the proportion of true positives over the total number of positives (both true and false positives)
- Let P denote precision
$$
P = \frac{TP}{TP+FP}
$$
Recall is the proportion of true positives over the total number of correct predictions (both true positives and false negatives)
- Let R denote recall
$$
R = \frac{TP}{TP+FN}
$$
