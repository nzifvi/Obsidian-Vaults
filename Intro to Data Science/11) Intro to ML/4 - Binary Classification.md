
---
# Binary Classification Notation
In simplest case, we have 2 labels.
- positive, denoted as +.
- negative, denoted as -.

By convention, class of interest is labelled as positive.
- Class not of interest labelled as negative.

Binary classification's task: label instances, $\forall x\in X$,with one or the other class labels.

# Classification with Logistic Regression
Output of logistic regression is the predicted probability.

Logistic function, aka sigmoid function:
$$
\sigma(t) = \frac{1}{1+e^{-t}}
$$

To obtain a classification between + and -, a threshold is applied by default:
- 0.5 by default...

$$
\sigma(w\cdot x) < 0.5 \Rightarrow \hat{y} = 0 
$$

$$
\sigma(w\cdot x) \geq 0.5 \Rightarrow \hat{y} = 1 
$$
By convention, sigmoid function predicts the positive class.


Cannot use typical linear regression for a binary classifier...
- Linear regression assumes data is normally distributed. It may not be.
- Linear regression can produce predictions outside the range of  $[0,1]$ which violates a probability axiom.

# Training a Binary Classifier
In practice the target function used to classify between the two classes, $f$, is unknown.
- All that is known is a training set of labelled instances: $(x, f(x))$.
	- A set of manually annotated examples used to train a model.

A model will use the examples to learn to approximate the target function: $\hat{f} : X \rightarrow C$

$\hat{f}$ will approximate the target function $f$.
- Over multiple training iterations, will increasingly approximate the target function more accurately. 
- Should be trained until $\hat{f}$ can generalise the whole of the instance space and unseen examples which are not part of the instance space.

# Accuracy and Error of a Binary Classifier
Use a contingency table, aka a confusion matrix.
![[Pasted image 20251118113518.png]]

Accuracy: proportion of correctly predicted instances / total instances.
Error: proportion of incorrectly predicted instances / total instances.


$$
Accuracy=\frac{(Actual_{+}, Predicted_{+})+(Actual_{-}, Predicted_{+})}{150}
$$
$$
Error=\frac{(Actual_{+}, Predicted_{-})+(Actual_{-}, Predicted_{-})}{150}
$$

Accuracy is important. However, both accuracy and error is equally important.
- If only caring about accuracy, false positives will be disregarded.
- Bad for situations where somebody's life can be ruined by a simple false positive: man gets arrested as binary classifier identifies him as a criminal due to false positive.

Per-Class accuracy is a more precise metric to evaluate the performance of a binary classifier. 

True positive rate (TPR), aka sensitivity, is the ratio of correctly predicted positive instances over total identified positive instances.
$$
TPR = \frac{(Actual_{+}, Predicted_{+})}{(Actual_{+}, Predicted_{-}) + (Actual_{+}, Predicted_{+})}
$$
- False positive rate (FPR) is the ratio of incorrectly predicted positives instances over total identified positive instances.

True negative rate (TNR), aka specificity, is the ratio of correctly predicted negative instances over total identified negative instances.

$$
TNR=\frac{(Actual_{-}, Predicted_{-})}{(Actual_{-}, Predicted_{-}) + (Actual_{+}, Predicted_{-})}
$$