 [[1) What makes a Probability Distribution a Discrete one]] <- Back

---
## What is a Binomial Distribution?
A Bernoulli Distribution models the probability of an outcome of a binary random variable occurring in a single trial.

A binomial distributions models the probability, of a binary random variable, occurring k times out of n trials.
- It uses a Bernoulli Distribution

## Calculating a Binomial Distribution's probability
Suppose a fair coin is flipped three times, what is the probability that 3 of 5 flips have an heads outcome
- Type of question a binomial distribution answers.

| $C = c$ | $P(C=c)$ |
| ------- | -------- |
| H       | 0.5      |
| T       | 0.5      |
![[Pasted image 20250420161048.png]]

Each purple line represents a trial.

One of the possible combinations you can get 3 heads, out of 5 total coin flips, is...

![[Pasted image 20250420161116.png]]

Which results in...

![[Pasted image 20250420161151.png]]

$$
P(X=H) \cdot P(X=H) \cdot P(X=H) \cdot P(X=T) \cdot P(X=T) = P(X=H)^{3} \cdot P(X=T)^{2}
$$

The product $P(X=H)^{3} \cdot P(X=T)^{2}$ is NOT the probability that, out of 5 coin flips, you get 3 heads.
- It is the probability of getting 3 desired outcomes (k), out of n trials, in that SPECIFIC combination.

To get the probability of getting k outcomes out of n trials, the probability of getting 3 desired outcomes (k), out of n trials, in that specific combination must be multiplied by the possible number of combinations of k outcomes out of n trials...

![[Pasted image 20250420161712.png]]

10 possible combinations of outcomes...

$$
X\backsim Bin(k = 3, n=5) = 10 \cdot (P(X=H)^{3} \cdot P(X=T)^{2})
$$
Giving the probability of getting 3 heads out of 5 coin flips...



## Building a Binomial Distribution
Using the above process, an ENTIRE binomial probability distribution can be generated for all possible trials (k) such that...

$$
0 \leqslant k \leqslant n
$$
- k must be less than or equal to 0 and less than or equal to n.
- n being the total number of trials possible.

The binomial probability, $X \backsim Bin(k = k, n = n)$, has an equation which produces the probability of each possible number of trials k.

$$
X\backsim Bin(K = k, N = n) = ^{n}C_{k} \cdot p^{k}\cdot (1-p)^{n-k}
$$

![[Pasted image 20250420165435.png]]
Where, from the Bernoulli Distribution used to form the Binomial Distribution...
- p represents the probability of the outcome associated as success.
- 1 - p represents the probability of the outcome associated as a failure.
- With that in mind, the binomial function can be rewritten as...

$$
X\backsim Bin(K = k, N = n) = ^{n}C_{k} \cdot P(X = "success")^{k}\cdot P(X="failure")^{n-k}
$$
Using this formula, the ENTIRE binomial probability distribution can be built...

$$
X\backsim Bin(k = 0, n = 5) = ^{5}C_{0} \cdot 0.5^{0}\cdot (0.5)^{5-0} = 0.03125
$$
$$
X\backsim Bin(k = 1, n = 5) = ^{5}C_{1} \cdot 0.5^{1}\cdot (0.5)^{5-1} = 0.15625
$$
$$
X\backsim Bin(k = 2, n = 5) = ^{5}C_{2} \cdot 0.5^{2}\cdot (0.5)^{5-2} = 0.3125
$$
$$
X\backsim Bin(k = 3, n = 5) = ^{5}C_{3} \cdot 0.5^{3}\cdot (0.5)^{5-3} = 0.3125
$$
$$
X\backsim Bin(k = 4, n = 5) = ^{5}C_{4} \cdot 0.5^{4}\cdot (0.5)^{5-4} = 0.15625
$$
$$
X\backsim Bin(k = 5, n = 5) = ^{5}C_{5} \cdot 0.5^{5}\cdot (0.5)^{5-5} = 0.03125
$$

| $K = k$ | $X \backsim Bin(K=k, N=5)$ |
| ------- | -------------------------- |
| 0       | 0.03125                    |
| 1       | 0.15625                    |
| 2       | 0.3125                     |
| 3       | 0.3125                     |
| 4       | 0.15625                    |
| 5       | 0.03125                    |

If built correctly, all possible trials will have the sum of 1.
## Characteristics of the Binomial Distribution

1) If whatever a Binomial distribution, $X \backsim Bin(K=k, N=n)$, models is 100% fair and unbiased. The bell curve it forms will be symmetrical.
	- Will be symmetrical about the expected value of K: \[K]

```chart
type: bar
labels: [K=0, K=1, K=2, K=3, K=4, K=5,]
series:
	- title: X~Bin(K=k, N=5)
	  data: [0.03125, 0.15625, 0.3125, 0.3125, 0.15625, 0.03125]
```

$$
[K] = \frac{0+1+2+3+4+5}{6} = 2.5 
$$
![[Pasted image 20250420163817.png]]
The bell curve on the left of the axis of symmetry will be identical to the bell curve on the right of the axis of symmetry
- Axis of symmetry = \[K]

2) If whatever the Binomial Distribution models is BIASED, aka unfair, the Binomial Distribution will be asymmetrical.

Let the following Bernoulli Distribution, $P(X=x)$, denote the probability of flipping a coin and getting a heads, $X=H$, or getting a tails, $X=T$

| $X=x$ | $P(X=x)$ |
| ----- | -------- |
| H     | 0.7      |
| T     | 0.3      |
Let X=H be the success outcome.
Let X=T be the failure outcome.

| $K = k$ | $X \backsim Bin(K=k, N=5)$ |
| ------- | -------------------------- |
| 0       | 0.00243                    |
| 1       | 0.02835                    |
| 2       | 0.1323                     |
| 3       | 0.3087                     |
| 4       | 0.36015                    |
| 5       | 0.16807                    |

```chart
type: bar
labels: [K=0, K=1, K=2, K=3, K=4, K=5,]
series:
	- title: X~Bin(K=k, N=5)
	  data: [0.00243, 0.02835, 0.1323, 0.3087, 0.36015, 0.16807]
```

\[K] = 2.5

![[Pasted image 20250420164621.png]]

Note that the Binomial Distribution is NOT symmetrical about the axis of symmetry. It is asymmetrical.
- Meaning: whatever the Binomial Distribution is modelling is biased: something wrong, such as cheating/rigging, is happening.

If asymmetrical...
- If bell curve leans to the right of the axis of symmetry, it is more probable to have MORE successful k trials.

- If bell curve leans to the left of the axis of symmetry, it is more probable to have MORE failure k trials.

