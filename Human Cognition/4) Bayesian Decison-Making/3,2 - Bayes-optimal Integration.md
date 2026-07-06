[[3,1 - Bayesian Probability]] $\leftarrow$ Back


---
# What is Bayes-optimal Integration?
Bayes-optimal integration combines two distributions (sources of information) according to their relative reliability (precision.)


Let...
- $\beta$ denote precision.
- $\mu$ denote mean.

Precision, $\beta$, is equal to $\frac{1}{\sigma^2}$ ($\sigma^2$ denotes variance)

For 
- Prior $P(H) \sim \mathcal{N}(\mu_{prior}, \frac{1}{\beta_{prior}})$
- Likelihood $P(data|H) \sim \mathcal{N}(\mu_{data}, \frac{1}{\beta_{data}})$

The posterior precision, $\beta_{posterior}$ is equal to...
$$
\beta_{posterior}=\beta_{prior}+\beta_{data}
$$
The posterior mean, $\mu_{posterior}$, is equal to...
$$
\mu_{posterior}=\frac{\beta_{prior}}{\beta_{posterior}}\mu_{prior}+\frac{\beta_{data}}{\beta_{posterior}}\mu_{data}
$$

The posterior...
$$
P(H|data)\sim\mathcal{N(\mu_{posterior}, \frac{1}{\beta_{posterior}})}
$$

# Interpreting Meaning from Posterior of Bayes-optimal Integration
Given 2 noisy signals, or distributions, bayes-optimal integration can combine the 2 signals in a way which weights each signal by how RELIABLE it is.
- More reliable signals have a higher precision.
- Less reliable signals have a lower precision.

$$
f(\sigma^2)=\frac{1}{\sqrt{\sigma^2}}
$$
$$
\beta=\frac{1}{\sigma}
$$
$$
\lim_{\sigma^2\rightarrow 0}\biggr[f(\sigma^2)\biggr] = \infty
$$
Recall $f(\sigma^2) = \beta$

So...
$$
\lim_{\sigma^2\rightarrow 0}\biggr[\beta\biggr]=\infty
$$

Defining the relationship...
>As $\beta_{a} \rightarrow \infty$, posterior $\rightarrow$ a
- The higher the precision, the more reliable a signal is.
- Posterior will increasingly approximate a signal the more reliable it comes, leaning away from the other.


