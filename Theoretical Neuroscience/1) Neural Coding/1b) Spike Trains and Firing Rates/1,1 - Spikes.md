[[1,2 Firing Rates as Spike-Count Rate]] $\leftarrow$ Next

#Spikes #SpikeMath

---
# APs as Information
APs convey information using their timing.
- Action potentials vary in duration, amplitude, and shape.
- APs are treated as identical events in neural encoding studies.

# Spike Sequences & Representation
AP sequences can be defined as a time sequence, T, of times when spikes occurred from a given neuron.
- Ignore brief duration of AP: approx 1ms.

For n spikes, the spike times are denoted as $t_i$ where i = 1,2,...,n
- Trial where spikes are recorded are assumed to start at time 0 ($t_1 = 0$)
- Trial where spikes are recorded are assumed to end at time T $(t_n = T)$


Spike sequence can also be represented as the sum of infinitely small, ideal spikes using the Dirac ($\delta$) function.
$$
ρ(t) = \sum_{i=1}^{n}\biggr[\delta(t-t_i) \biggr]
$$
- $ρ(t)$ is the neural response function (NRF).
	- used to re-express sums over spikes as integrals over time.

For any function $f(t)$...
$$
\sum_{i=1}^{n}\biggr[f(t-t_i)\biggr] = \int_{-\infty}^{\infty}\biggr[f(\tau)ρ(t-\tau)\biggr]d\tau
$$

The spike sequence varies from trial to trial, despite being presented same stimulus.
- Neural responses treated as statistical or probabilistic.

# Spike Sequences in Reality
The NRF is impossible to calculate in reality, due to...
1) Infinite height at spike times, due to the Dirac function.
2) Infinite width.
3) Integral of EXACTLY 1 per spike.

Since this is the case, the NRF is quantised (approximately represented), and represented as $p[k]$, such that...
$$
p(t) \approx p[k]
$$

To quantise the NRF, the continuous time domain of $[0, T]$ is discretised into bins of width $\Delta t$
$$
[0, \Delta t), [\Delta t, 2\Delta t),...
$$
- Each bin covered by an integer k. The $k^{th}$ bin covers...
$$
[k\Delta t, (k+1)\Delta t)
$$

$$
p[k] = \frac{1}{\Delta t}\sum_{i=1}^n \bigg[1f(t_i, k)\bigg]
$$
$$
f(t_i, k) = \begin{cases} k\Delta t \leq t_i < (k+1)\Delta t \Rightarrow f(t_i, k) = 1 \\
\text{Else 0}
\end{cases}
$$

$$
c[k]=\sum_{i=1}^{n}f(t_i, k)
$$
$c[k]$ counts how many spikes fall into bin k.
- $p[k]$ simplifies to...
$$
p[k]=\frac{1}{\Delta t}c[k]
$$

Where...
- T is the total duration of the simulation.
The total number of possible bins, K, is equal to...
$$
K= \text{floor}\bigg(\frac{T}{\Delta t} \bigg)
$$
The bin index itself is calculated using function k for a time value
$$
k(t) = \text{floor}\bigg(\frac{t}{\Delta t}\bigg)
$$