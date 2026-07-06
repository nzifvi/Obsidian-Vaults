[[4,2 - Naïve Bayes Classifiers Parameters]] $\leftarrow$ Back

---
# Logistic Regressors for Document Classification
Logistic regression can be used to classify if a document is or is not a type.
- Logistic regression can only handle binary classification: is X or is not X.

Logistic regression requires inputs which are...
1) Numeric.
2) Come in a fixed amount. There cannot be a variable number of inputs.

To enable logistic regression, a document vector must be used.
- Document vectors represent the contents of a document numerically. 
- Fixed-length document vectors must be used

Some fixed-length document vectors are...
1) Bag-of-Words
2) TF-IDF
3) Others exist.

# Creating a Logistic Regression Model for Document Classification
1) Create n weights, denoted as $\vec{\theta}_{n\times1}$.
	- n is the number of words in the vocabulary all document vectors are created with.