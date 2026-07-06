[[4,1 - Naïve Bayes Classifiers]] $\leftarrow$ Back
[[5,1 - Logistic Regression Classifiers]] $\leftarrow$ Next

---
# Parameters
Parameters of Naïve Bayes model:

- Prior probabilities of classes: $P(c)$
- Class conditional probabilities for EACH feature: $P(f|c)$

Distributions are derived, from labelled training data, using Maximum Likelihood Estimation (MLE)

# Estimating Priors
Suppose...
- we have k documents in the training sample:
$$
D=\{d_1,...,d_k\} \Rightarrow |D|=k
$$
- For each document, $d_i$, the class of the document is known:
$$
\forall d, d\in D | label(d)=c
$$
The MLE for $P(c_i)$ = proportion of documents with label $c_i$ over the cardinality of documents set

$$
P(c_i)=\frac{|\{d|label(d)=c\}|}{k}
$$

To build the ENTIRE prior distribution, cover for all possible classes.

| C     | P(C)     |
| ----- | -------- |
| $c_1$ | $P(c_1)$ |
| $...$ | $...$    |
| $c_n$ | $P(c_n)$ |
## Example
$$
|D|=100
$$
- 40 documents labelled as positive.
- 60 documents labelled as negative.

$$
C=\{positive, negative\}
$$
$$
P(C=positive)=\frac{40}{100}=\frac{4}{10}=\frac{2}{5}
$$
$$
P(C=negative)=\frac{60}{100}=\frac{6}{10}=\frac{3}{5}
$$
| C        | P(C)          |
| -------- | ------------- |
| positive | $\frac{2}{5}$ |
| negative | $\frac{3}{5}$ |

# Estimating Conditional Probabilities 
For each feature, want to calculate the probability of it occurring given a knowledge of each class.
$$
P(f|c)
$$

To estimate conditional probabilities...
- Label of each document, $label(d_i)$, must be known.
- Features of each document, $features(d_i)$ must be known.

3 different event models exist to estimate the conditional probabilities:
1) Bernoulli Model
2) Multinomial Model
3) Multinomial Model truncated to 1.

## Bernoulli Naïve Bayes Model (BNBM)
BNBM only considers whether a feature is or is not in a document.
- Document represented as a vector of Booleans. Each feature is a Boolean variable.

$$
\vec{d_i} = \begin{bmatrix}present(f_1)\\...\\present(f_n)\end{bmatrix}
$$

MLE for conditional probability, $P(f_i|c)$, is proportion of documents labelled with class c that have feature $f_i$ over the number of documents labelled with class c.

$$
P(f_i|c)=\frac{|\{i|label(d_i)=c \wedge f_i\in features(d_i)\}|}{|\{i|label(d_i)=c\}|}
$$

### Pseudocode
```pseudocode
procedure: calculateMLEConditionalProbability
inputs: D[0,...,n-1] (a list of documents), f (desired feature), c (desired class)
outputs: P(f|c)


docsWithFeature <- []
docsWithClass <- []

for (i <- 0 to n-1) do:
	if (label(D[i]) = c and f is in features(D[i])):
		docsWithFeatures.insertLast(D[i])
	if (label(D[i]) = c):
		docsWithClass.insertLast(D[i])

return size(docsWithFeatures) / size(docsWithClass)
```

# Multinomial Naïve Bayes Model (MNBN)
MNBN considers all occurrences of a feature in a document.
- Document is represented as a vector of counts, one for EACH feature in that document.

$$
\vec{d_i}=\begin{bmatrix}count(f_1)\\...\\count(f_n)\end{bmatrix}
$$
MLE for conditional probability, $P(f_i|c)$, is proportion of the count of feature $f_i$ in documents, labelled with class c, over the sum of all count of features

$$
P(f_i|c)= \frac{count(c, f_i)}{\sum_{i=1}^n\biggr[count(c, f_i)\biggr]}
$$

$$
\forall i, i \in \mathbb{N} | 1 \leq i \leq |D|
$$
