[[2,1) Applying Bayes Theorem]] <- Back

---
## Producing Conditional Probability Distribution

Multiple methods to build a conditional probability distribution exist. Which one to use depends on the circumstances you find yourself in.


## 1) From a Joint Distribution
If the joint distribution of the 2 events is known, it can be used to produce both conditional distributions.
Suppose you have event A, B.

Joint distribution: $P(A,B)$

Can be used to produce both conditionals of the events A,B: $P(A|B)$, $P(B|A)$

Using the formula...

$$
P(A|B) = \frac{P(A,B)}{P(B)}
$$
- Divide the joint distribution by the prior distribution you want to be the given part of the conditional.




## 2) From Observed Data
If a dataset of paired observations exist, you can produce a joint via processing the data.

Paired observation = n-tuple of events with an outcome.

Suppose for each time a person is drunk, we also check if the drunk person gets a kebab.

Let random variable...
	$D \in \{T, F\}$ represent the 2 possible outcomes, T (is drunk) and F (is not drunk)
	$K \in \{T, F\}$ represent the 2 possible outcomes, T (has kebab), and F (doesn't have kebab)

$$
O =\{(T,T), (F, F), (F, F), (F, T), (T, T), (T, F), (T, T)\}
$$
- let O represent the set of observation tuples.

Produce the joint frequency table...
- Lists how many times each possible combination of random variables occurred in the set of tuples.
- Can solve how many columns are expected by using...

$|D|! + |K|! = 4$
- 4 expected rows (4 possible unique combinations of random variable outcomes)
$$
\{(T,T), (F, F), (F, F), (F, T), (T, T), (T, F), (T, T)\}
$$

| D = d | K = k | Count |
| ----- | ----- | ----- |
| T     | T     | 3     |
| T     | F     | 1     |
| F     | T     | 1     |
| F     | F     | 2     |
Convert the joint frequency table into a joint probability distribution by dividing EACH count by the total number of observation tuples...

| D = d | K = k | P(D = d, K = k)   |
| ----- | ----- | ----------------- |
| T     | T     | $\frac{3}{\|O\|}$ |
| T     | F     | $\frac{1}{\|O\|}$ |
| F     | T     | $\frac{1}{\|O\|}$ |
| F     | F     | $\frac{2}{\|O\|}$ |
$|O| = 7$

| D = d | K = k | P(D = d, K = k) |
| ----- | ----- | --------------- |
| T     | T     | $\frac{3}{7}$   |
| T     | F     | $\frac{1}{7}$   |
| F     | T     | $\frac{1}{7}$   |
| F     | F     | $\frac{2}{7}$   |
Giving the joint distribution $P(D, K)$

From the joint distribution, the prior distributions, aka marginal distributions, can be solved by summing over the joint in a specific way.
- Suppose you want to get the prior distribution P(D)
- For each outcome of D, let it remain constant whilst the other random variables go through each combination.
- The sum of the above process provides the probability for that outcome of D.
- Repeat for all possible outcomes of D.

$$
P(D = T) = P(D = T, K = T) + P(D=T,K=F)
$$
$$
P(D = F) = P(D = F, K = T) + P(D=F,K=F)
$$
Giving us...

| D = d | P(D = d)      |
| ----- | ------------- |
| T     | $\frac{4}{7}$ |
| F     | $\frac{3}{7}$ |
All possible prior probability distributions can be built from the joint...

$$
P(K = T) = P(K=T, D=T) + P(K=T, D=F)
$$
$$
P(K = F) = P(K=F, D=T) + P(K=F, D=F)
$$

| K = k | P(K = k)      |
| ----- | ------------- |
| T     | $\frac{4}{7}$ |
| F     | $\frac{3}{7}$ |
With the joint probability and prior probability distribution, a conditional probability distribution can be built using the approach discussed in 1) From a Joint Distribution

$$
P(K = k|D = d) = \frac{P(D = d, K = k)}{P(D = d)}
$$
Must produce the probability for each possible outcome of random variables K, D...

$$
P(K=T|D = T) = \frac{P(D=T, K=T)}{P(D=T)} = \frac{3}{4}
$$
$$
P(K=T|D = F) = \frac{P(D=F, K=T)}{P(D=F)} = \frac{1}{3}
$$

$$
P(K=F|D = T) = \frac{P(D=T, K=F)}{P(D=T)} = \frac{1}{4}
$$
$$
P(K=F|D = F) = \frac{P(D=F, K=F)}{P(D=F)} = \frac{2}{3}
$$
Giving us the conditional probability distribution $P(K|D$

| K = k | D = d | P(K = k\|D = d) |
| ----- | ----- | --------------- |
| T     | T     | $\frac{3}{4}$   |
| T     | F     | $\frac{1}{3}$   |
| F     | T     | $\frac{1}{4}$   |
| F     | F     | $\frac{2}{3}$   |
To check if a conditional probability distribution has been built correctly, you can check by...
- Holding a given variable constant, for example let D = T.
- Summing over all possible combinations of the target variable.
- The sum should equal 1 if built correctly...

$$
P(K=T|D=T) + P(K=F|D=T) = \frac{3}{4} + \frac{1}{4} = 1
$$

Repeat check for all possible outcomes of the conditional's given variable.
- If each have a sum of 1, conditional probability distribution is correct.
## 3) From another Conditional Probability Distribution and a Prior Probability Distribution

## 4) Assume Independence

