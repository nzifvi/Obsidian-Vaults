[[1,2 Firing Rates as Spike-Count Rate]] $\leftarrow$ Back
[[1,4 - Measuring Firing Rates]] $\leftarrow$ Next

---
# Time-dependent Firing Rate (TdFR)
A time-dependent firing rate can be calculated by counting the frequency of all the spikes that occurred between time t and time $t+\Delta t$.

TdFR allows for high temporal resolution, unlike SCR, using a small $\Delta t$.
- Small $\Delta t$ results in a spike count in a given trial being 0 or 1, giving only 2 possible firing rates.
- Solution is to average across multiple trials using the SAME $\Delta t$.
- Therefore, the TfDR is defined as the average number of spikes appearing during a short interval between times $t$ and $t+\Delta t$ DIVIDED by duration of interval.

## Calculating Trial Average
The number of spikes occurring between times $t$ and $t+\Delta t$, on a single trial, is the integral of the neural response function over the time integral.

The AVERAGE number of spikes, during this interval, is the integral of the trial avg. neural response function: $\bar{ρ}(\tau)$


## Final Calculation of TfDR
TfDR is denoted as r(t): NOT THE SAME AS SCR.
$$
r(t) = \frac{1}{\Delta t} \int_{t}^{t+\Delta t}\biggr[\bar{ρ}(\tau)\biggr]d\tau
$$
# Quantising TfDR
To calculate the firing rate, within a window of $t$ to t+W, it must be quantised as well.
- W is the window size.
- $\Delta t$ is the time bin width.
$$
\int_{t}^{t+W}\bar{ρ}(\tau) d\tau \approx \Delta t \sum_{k=k(t)}^{k(t+W)}\bigg[\bar{p}[k]\bigg]
$$

$$
\bar{p}[k]=\frac{\bar{c}[k]}{\Delta t}
$$
Where $\bar{c}[k]$ is the trial-averaged spike count in bin k.
- With M trials, each with their own spike times...
	1) Quantise each trial separately to get $c_m[k]$
	2) Average across all trials to produce $\bar{c}[k]$
