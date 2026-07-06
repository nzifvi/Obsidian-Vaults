[[1,3 - Firing Rates as Time-dependent Firing Rate]] $\leftarrow$ Back

---
# Measuring Firing Rates
TfDR firing rate, r(t), cannot be EXACTLY determined from limited data from limited no. of trials.
- No unique way exists to approximate r(t).

Therefore, metrics such as SCR and TfDR require discretised varients of the neural response function: $p[k]$

To discretise, the continuous time domain is binned into K bins where...
- $T$ is the total time duration.
- $\Delta t$ is the bin width.

$$
K= \bigg\lfloor\frac{T}{\Delta t} \bigg\rfloor
$$
This defines K bins such that...
$$
0,1,...,K
$$
Let $f$ denote a function used to calculate a spike at a given time.
$$
c[k]= \sum_{i=1}^{n}\bigg[f(t_i, k)\bigg]
$$
- $c[k]$ calculates how many spikes fall into the $k^{th}$ bin based on what time they spiked at.

To produce a discrete trial-averaged spike train $\bar{c}[k]$ for bin k...
- Over M trials
$$
c_{m}[k] = \{c_1[k],...,c_{M}[k]\} 
$$
$$
\bar{c}[k]=\frac{1}{M}\sum_{m=1}^{M}\bigg[c_{m}[k]\bigg]
$$

These 2 variants of the spike count train function can be used to create 2 discretised neural response functions...
1) Discrete single-trial NRF
$$
p[k]=\frac{c[k]}{\Delta t}
$$

2) Discrete trial-averaged NRF
$$
\bar{p}[k] = \frac{\bar{c}[k]}{\Delta t}
$$

These can be used to calculate discretised SCR and TfDR.