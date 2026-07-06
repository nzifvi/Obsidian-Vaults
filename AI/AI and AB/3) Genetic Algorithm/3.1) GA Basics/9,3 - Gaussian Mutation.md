[[9,2 - Standard Mutation]] $\leftarrow$ Back
[[10 - Steady-State GAs]] $\leftarrow$ Next

---
# What is Gaussian Mutation?
Gaussian mutation introduces genetic diversity by adding a random value, drawn from a Gaussian distribution, to each gene in the genotype.
- Gaussian mutation works well with real-valued genes.

Gaussian mutation draws values from a standard Gaussian distribution
$$
N(\mu=1, \sigma=1)
$$
- Most values near zero.
- Larger values less likely.

Let $G$ denote a genotype such that...

$$
G=<g_1,...,g_{|G|}>
$$
$$
f(\Delta g_i)=\frac{1}{\sigma \sqrt{2\pi}}e^{-\frac{1}{2}\biggr(\frac{\Delta g_i - \mu}{\sigma}\biggr)^2}
$$

The mutation of a singular gene, $g_i$, is expressed as...
$$
g_i' = g_i + \Delta g_i
$$
An entire gene can be mutated by...
$$
G'=G+(Z\odot M)\cdot \sigma
$$
Where...
- $G$ is the current genotype. $G'$ is the mutated genotype.
- $Z \text{ is distributed as } N(\mu = 0, \sigma = 1)$   
- $M\in \{0, 1\}^n$ is a Bernoulli mask. Each element, $m_i$, is sampled from $Bernoulli(p)$ where p is the mutation rate.
- $\sigma$ (sigma) is the scaling factor.

# Adaptive Sigma
Adaptive sigma is a mechanism where the mutation step size, $\sigma$, is not fixed but is dynamic as the evolution progresses.
- If populations stuck in local optimum, increase $\sigma$ to encourage exploration.
	- Decreases selection pressure as $\sigma$ increases
- If population is consistently finding better solutions, decrease $\sigma$ to encourage exploitation.
	- Increases selection pressure as $\sigma$ decreases