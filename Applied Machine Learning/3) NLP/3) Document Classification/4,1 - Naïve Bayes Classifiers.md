[[3,4 - Automatically Derived Vocabulary List Classifiers]] $\leftarrow$ Back
[[4,2 - Naïve Bayes Classifiers Parameters]] $\leftarrow$ Next

---
# What is a Naïve Bayes Classifier
A naïve bayes classifier utilises Bayesian probability to classify documents

A data item to classify is viewed as a tuple, F, of features
$$
f=(f_1,...,f_n)
$$
Shorthand for features tuple with 1 to n items = $f_1^n$

There also exists a set of possible classes, C.
- Particular class $c | c \in C$

The goal is to assign a class, c, based on $F_1^n$, utilising Bayesian probability.
- Probability of something having class c given features $f_1^n$ is equal to...
$$
P(c|f_1^n)
$$

The most probable class, $c_{assumed}$, of a data item can be found by...
$$
C=\{c_1,...,c_m\}
$$
$$
f_1^n=(f_1,...,f_n)
$$
$$
c_{assumed}=max\biggr(P(c_1|f_1^n),...,P(c_m|f_1^n)\biggr)
$$
- The most probable class, $c_{assumed}$, is equal to the most probable conditional.

$$
P(c, f_1^n)=P(c,f_1^n)
$$
$$
P(c|f_1^n)\cdot P(f_1^n)=P(f_1^n|c)\cdot P(c)
$$
$$
P(c|f_1^n)=\frac{P(f_1^n|c)\cdot P(c)}{P(f_1^n)}
$$
Since we are taking the maximum for all possible classes, $c_1 \leq c_i \leq c_m$, the denominator is constant across all of them.
- Denominator does not impact what class is the maximum possible one, since they all have a common denominator
If...
$$
P(c_i|f_1^n)=\frac{P(f_1^n|c_i)\cdot P(c_i)}{P(f_1^n)}
$$
... then ...
$$
c_{assumed}=max\biggr(\frac{P(f_1^n|c_i)\cdot P(c_i)}{P(f_1^n)},...,\frac{P(f_1^n|c_m)}{P(f_1^n)}\biggr)
$$
because ALL terms in the maximum function have the same denominator, it can be disregarded since it would EQUALLY have an impact on all terms if it were not disregarded.

Therefore...
$$
max\biggr(\frac{P(f_1^n|c)\cdot P(c)}{P(f_1^n)},...,\frac{P(f_1^n|c_m)}{P(f_1^n)}\biggr)\approx max\biggr(P(f_1^n|c_i)\cdot P(c_i),...,P(f_1^n|c_m)\cdot P(c_m)\biggr)
$$

# Naïve Bayes Assumption
The naïve assumption, in this case, is the assumption that every single feature, $f_i$, is INDEPENDENT of all of the other features.
- ASSUME: presence of one feature tells nothing about the presence of other features.

The naïve assumption allows for...

$$
P(f_i^n|c_j)\cdot P(c_j)=\prod_{i=1}^n\biggr[P(f_i | c_j)\cdot P(c_j)\biggr]
$$
- Means the entire joint distribution does not have to be calculated to solve for all values of $f_i^n$ : less computationally expensive.
- Reduces problem down to a single dimension, $f_i$, rather than all possible features $f_1$ to $f_n$ per conditional calculation.

Let...
$$
$$

ENTIRE equation simplifies to...


$$
c_{assumed}=max\biggr(\prod_{i=1}^n\biggr[P(f_i | c_1)\cdot P(c_1)\biggr],...,\prod_{i=1}^n\biggr[P(f_i | c_m)\cdot P(c_m)\biggr]\biggr)
$$
