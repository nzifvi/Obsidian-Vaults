[[1) What makes a Probability Distribution a Discrete one]] <- Back

---
## What is a Bernoulli Distribution?
Bernoulli Distribution = simplest and most fundamental discrete probability distribution.
- Models a random experiment, aka sample space, with exactly 2 possible outcomes.
	- Outcome 1: "success", aka T or 1
	- Outcome 2: "failure", aka F or 0

What outcome is a success, or failure, is up to choice.
- Only 1 can be success, only 1 can be failure.


Bernoulli Distribution models probability for a random variable to be either of the 2 possible outcomes.
- Only binary outcomes can be modelled.
- Little trick does exist to model non-binary possible outcomes of a random experiment/sample space with Bernoulli Distribution though.

Bernoulli Distribution describes the outcome of a single trial or experiment (flipping a coin again, whether a light is on or off, getting a specific outcome out of n outcomes, etc).

## Presenting Bernoulli Distributions

### 1) By Value

$$
P(X=T) = p
$$
where p = probability of success

$$
P(X=F) = 1-p
$$
1-p = probability of failure

### 2) By Table

Let $P(X=x)$ be a Bernoulli Probability Distribution.
$$
X\in \{T, F\}
$$
Let T represent success outcome.
Let F represent failure outcome

| $X=x$ | $P(X_{1}=x)$ |
| ----- | ------------ |
| T     | p            |
| F     | 1-p          |
### 3) By Histogram

Let $P(X=x)$ be a Bernoulli Probability Distribution
$$
X\in \{T, F\}
$$
Let T represent success outcome.
Let F represent failure outcome

$P(X=T) = 0.7$
$P(X=F) = 0.3$

```chart
type: bar
labels: [X=T, X=F]
series:
	- title: P(X=x)
	  data: [0.7, 0.3]
```


## Why is Bernoulli Distribution the most Fundamental Distribution?

Bernoulli Distribution = the most fundamental distribution as...

1) It models the most simple of things in terms of probability
	- A "yes or no", "true or false", "this or that", kind of probability.

2) It is used in many other kind of probability distribution.
	- Many other probability distributions use a Bernoulli Distribution to be built.

## Using Bernoulli Distribution to model non-binary possible outcomes

Although Bernoulli Distributions only model random experiments, or sample spaces, with binary possible outcomes, a workaround exists to model non-binary possible outcomes.

Suppose you have a sample space, S, which models the possible outcomes of a dice spin...

$$
S=\{1, 2, 3, 4, 5, 6\}
$$

Let random variable X denote an outcome for a trial of S.

$$
X\in S
$$

On it's own, a Bernoulli Distribution cannot be used to model the probability of a an outcome of a non-binary random variable, you can modify the random variable to make it work for Bernoulli Distributions

Suppose, instead of random variable X being a possible outcome from sample space S...

It now models an outcome being 6 or not 6.
- This is now a binary random variable, allowing it to be used in a Bernoulli Distribution.

$$
X_{1} \in \{6, \lnot6 \}
$$

This can be done for all possible outcomes of the original random variable...

$$
X_{2} \in \{5, \lnot5\}
$$
$$
X_{3} \in \{4, \lnot4\}
$$
$$
X_{4} \in \{3, \lnot3\}
$$
$$
X_{5} \in \{2, \lnot2\}
$$
$$
X_{6} \in \{1, \lnot1\}
$$

Presume that, from an experiment of S, we get a observation set...
$$
O = \{1, 1, 1, 2, 2, 3, 4, 5, 6, 1, 1, 2, 2, 2, 3\}
$$
A Bernoulli Distribution for each of the binary random variables we have formed, of sample space S, can be built...

USING NAIVE DEFINITION OF PROBABILITY...
- aka frequency probability definition

| $X_{1}=x$ | $P(X_{1}=x)$                                     |
| --------- | ------------------------------------------------ |
| $6$       | $\frac{\|\{x\| x\in O \land x=6\}\|}{\|O\|}$     |
| $\lnot6$  | $\frac{\|\{x\| x\in O \land x\neq 6\}\|}{\|O\|}$ |

| $X_{1}=x$ | $P(X_{1}=x)$    |
| --------- | --------------- |
| $6$       | $\frac{1}{15}$  |
| $\lnot6$  | $\frac{14}{15}$ |

| $X_{2}=x$ | $P(X_{2}=x)$    |
| --------- | --------------- |
| $5$       | $\frac{1}{15}$  |
| $\lnot5$  | $\frac{14}{15}$ |

| $X_{3}=x$ | $P(X_{3}=x)$    |
| --------- | --------------- |
| $4$       | $\frac{1}{15}$  |
| $\lnot4$  | $\frac{14}{15}$ |

| $X_{4}=x$ | $P(X_{4}=x)$    |
| --------- | --------------- |
| $3$       | $\frac{2}{15}$  |
| $\lnot3$  | $\frac{13}{15}$ |

| $X_{5}=x$ | $P(X_{5}=x)$    |
| --------- | --------------- |
| $2$       | $\frac{5}{15}$  |
| $\lnot2$  | $\frac{10}{15}$ |

| $X_{6}=x$ | $P(X_{6}=x)$    |
| --------- | --------------- |
| $1$       | $\frac{5}{15}$  |
| $\lnot1$  | $\frac{10}{15}$ |
