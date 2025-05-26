[[1) What makes a Probability Distribution a Discrete one]] <- Back

---
## What is a Poisson Distribution?

A Poisson Distribution, $X \back$sim Po(X = k) , provides the probability that k events occur within a time interval t.

The type of problem the Poisson distribution is for:
- What is the probability that k events occur every t time.

### Poisson Mean and Variance
To calculate a Poisson Distribution, the Poisson's mean
- From the mean, the variance and standard deviation can be calculated.

$\lambda$ denotes the Poisson's mean.

$$
\lambda = \frac{k}{t}
$$
where k = expected number of events.
and
where t = time interval.

With the Poisson Distribution, the mean is equal to the variance.

## Calculating the Poisson Distribution

$$
X \backsim Po(X=k) = \frac{\lambda^{k} \cdot e^{-\lambda}}{k!}
$$
k = number of events interested in
"what's the probability that k events occur"

$\lambda$ = approximate rate, mean, of events occurring in time interval t.

Suppose we want to know...
"What is the probability of 5 buses arriving every 2 hours"

From the above question, the number of events we are interested in, k "buses arriving", equals 5.

The time interval interested in is 2 hours. t = 2

$$
\lambda = \frac{5}{2} = 2.5
$$

$$
X \backsim Po(X=5) = \frac{2.5^5 \cdot e^{-2.5}}{5!} = 0.0668
$$

Therefore, the probability that 5 buses arrive in 2 hours is 0.0668

An entire distribution can be built, from k = 0 to k -> $\infty$

| $X = k$ | $X \backsim Po(X=k)$ |
| ------- | -------------------- |
| 0       | 0.08208              |
| 1       | 0.20521              |
| 2       | 0.257                |
| 3       | 0.214                |
| 4       | 0.134                |
| 5       | 0.067                |
| 6       | 0.028                |
| 7       | 0.010                |
```chart
type: bar
labels: [K=0, K=1, K=2, K=3, K=4, K=5, K=6, K=7]
series:
	- title: X~Po(X=k)
	  data: [0.082, 0.205, 0.257, 0.214, 0.134, 0.067, 0.028, 0.010]
```

## Characteristics of the Poisson Distribution

1) In the Poisson Distribution, the most probable k value, $k_{most-probable}$ , has an equivalent probability to $k_{most-probable} - 1$ 

2) Poisson Distribution has an asymptote at y = 0.
	- Means that the sum of a Poisson Distribution $\neq$ 1 ever
	- Additionally, as k -> $\infty$, $X \backsim Po(X=k)$ -> 0
	- There are an infinite possible values of k, the number of expected events. There are an infinite number of expected events that are possible.

3) k can equal 0, because the probability of no expected events can exist mathematically.

4) The domain of k begins at 0 and has an upper bound of infinity.

## Manipulating $\lambda$ : the mean
The mean, $\lambda$, can be represented in 2 ways.

1) As a mean number of events over the time interval.

$$
\lambda = \frac{k}{t}
$$
Event occurs k times over t time.

2) As a rate

Let k = 5 buses
Let t = 2 hours
$$
\lambda= \frac{5}{2}
$$

Giving...

$$
\lambda = 2.5\frac{buses}{h}
$$
The lambda in itself is a rate. The rate can be manipulated to change what the Poisson Distribution models by converting between units.

$$
2.5\frac{buses}{h} \cdot \frac{24h}{d} = 2.5\frac{24 \cdot buses \cancel{h}}{d} = 60 \frac{buses}{d}
$$

Now the Poisson Distribution, using the newly manipulated mean, can be used to model the probability of k buses arriving in a day.

