[[4,1) Counting Outcomes]] <- Back
[[6) Frequency and Bayesian Probability]] <- Next

---
## Non-Naïve Definition of Probability
The Naïve definition of probability is only applicable when...
1) All possible outcomes of a sample space, S, are equally likely to occur.
2) When the cardinality of sample space, S, is finite.


If all possible outcomes are not equally likely, the naïve definition does not apply anymore.

If the sample space, S, is not finite then naïve probability cannot even be calculated.


For probability to work, a set of axioms must be upheld. If any of these axioms violated, probability will be wrong.
- From these axioms, probability functions can be formed to solve the probability of an outcome.

## Axioms of Non-Naïve Probability
#### 1) Probability, of all outcomes, must sum to 1.
If the probability of all possible outcomes is summed, the outcome must equal to 1.

$$
X \in \{1, 2, 3, .... n\} \Rightarrow \sum P(X) = 1
$$

#### 2) In an empty sample space, S, the probability of all outcomes must sum to 0
$$
X \in \emptyset \Rightarrow P(X) = 0
$$

#### 3) If $A_{1}, A_{2}$ are disjoint events, then...
Disjoint events are 2, or more, events that cannot occur simultaneously. An example of this is rolling a dice. You can only make one roll per event, thus, each event is disjoint. 
$$
S = \{x_{1}, x_{1},..., x_{n}\}
$$

For sets, which events are in this case, to be disjoint, they are mutually exclusive. This means that...
$$
A_{i} \cap A_{j} = \emptyset, i \neq j
$$

$$
\bigcup_{i = 1}^{\infty}[A_{j}] = \sum_{i = 1}^{\infty}[P(A_{i})]
$$

This allows the sum probability, of multiple disjoint events, to be summed

Example: Suppose you roll a dice, all outcomes are equal, what is the probability you get a 1, 2, 3, or 4 in a single roll.

$$
S = \{1, 2, 3, 4, 5, 6\}
$$

$$X \in S$$
$$
P(X=1, 2, 3, 4) = P(X = 1) + P(X = 2) + P(X = 3) + P(X = 4)
$$
$$
P(X=1,2,3,4) = \sum_{i = 1}^4P(X = i) 
$$
$$
P(X = 1, 2, 3, 4) = \frac{1}{6} + \frac{1}{6} + \frac{1}{6} + \frac{1}{6} = \frac{4}{6}
$$
Therefore, using the above rule...

$$
P(X = 1, 2, 3, 4) = \frac{4}{6}
$$
