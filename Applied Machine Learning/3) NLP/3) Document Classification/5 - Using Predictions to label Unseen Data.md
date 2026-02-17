[[4,2 - Naïve Bayes Classifiers Parameters]] $\leftarrow$ Back
[[6,5,1 - Evaluating Classifiers]] $\leftarrow$ Next

---
# Predicting Labels of Unseen Data
Given...
- An unseen, unlabelled document d.
- A model which has been trained and can be used to predict the label for d.
- Classes $C=\{c_1,...,c_m\}$

Let...
- Features of d = $\{f_1,...,f_n\}$

The label of d, $label(d)$, can be predicted via...
$$
label(d)=max\biggr(\prod_{i=1}^n\biggr[P(f_i|c_1)\cdot P(c_1)\biggr],...,\prod_{i=1}^n\biggr[P(f_i|c_m)\cdot P(c_m)\biggr]\biggr)
$$
