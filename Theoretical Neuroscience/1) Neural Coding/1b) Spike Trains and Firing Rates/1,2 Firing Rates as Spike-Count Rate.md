[[1,1 - Spikes]] $\leftarrow$ Back
[[1,3 - Firing Rates as Time-dependent Firing Rate]] $\leftarrow$ Next

---
# Firing Rates as Spike-Count Rate
Firing rates is a term which is used to describe many things.
- Simplest of these things is spike-count rate (SCR).

# Calculating SCR
SCR is the frequency of APs that appear during a trial, from a neuron, and then dividing that frequency by the total duration of the trial.
- SCR denoted as r.

SCR is equal to...
$$
r= \frac{n}{T} = \frac{1}{T}\int_{0}^{T}\biggr[ρ(\tau)\bigg]d\tau
$$Where n is the total spike count across time...
$$
n=\int_{0}^{T}\biggr[ρ(\tau)\bigg]d\tau
$$
The SCR is the time average of the neural response function OVER the duration of the trial.

# SCR Properties
SCR can be determined from a single trial. HOWEVER, at the cost of all temporal resolution about variance in the neural response being lost.

# Quantised SCR
Due to the same reasons that spikes cannot be continuously counted and must be quantised, SCR MUST be quantised.

$$
\int_{0}^{T}p(\tau)\Delta \tau \approx \Delta t \sum_{k=0}^{K-1}p[k]
$$
So...
$$
r\approx \frac{\Delta t}{T} \sum_{k=0}^{K-1}\bigg[p[k]\bigg]
$$
Recall...
$$
p[k] = \frac{c[k]}{\Delta t}
$$
- $\Delta t$ from the summand cancels the outside $\Delta t$, giving...

$$
r \approx \frac{1}{T}\sum_{k=0}^{K-1}\bigg[c[k]\bigg]
$$
$$
n \approx \sum_{k=0}^{K-1}\bigg[c[k]\bigg]
$$
