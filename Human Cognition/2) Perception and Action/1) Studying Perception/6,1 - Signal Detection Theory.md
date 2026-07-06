
#DPHC #DPHC-SDT #SDT

---
# What is Signal Detection Theory (SDT) ?
SDT is a simple model of two-choice tasks.
- SDT is used to make decisions when noise interferes with an actual signal.
- SDT is also used to discriminate between signal + noise versus noise.
	- Detects whether there is actually a signal present versus a signal absent.

SDT states that behaviour is a function of...
1) Task ability (sensitivity)
	- How good our perception is.
2) Response bias
	- Decision criterion (c) threshold.


SDT is often fitted to data to estimate sensitivity and response bias.

# Mathematical Model of SDT
Let...
- $f_s(x)$ denote the signal.
- $f_n(x)$ denote the noise.

> ASSUMPTION 1:
> 	SDT assumes that both the signal and noise are distributed as a Gaussian

$$
f_s(x) \sim \mathcal{N}(\mu_s, \sigma_s^2)
$$
$$
f_n(x) \sim \mathcal{N}(\mu_n, \sigma_n^2)
$$
> ASSUMPTION 2:
> 	Variances of noise and signal are equivalent and equal to 1.
> 		- NOT ALWAYS THE CASE. JUST TYPICALLY ASSUMED.

$$
\sigma_s^2 = \sigma_n^2 = 1
$$

The x domain represents internal evidence.
- A specific x value is a value of evidence.


A decision criterion, c, is defined.
- Determines the amount of evidence required to conclude whether a signal is present or absent.
$$
x \geq c \Rightarrow \text{"Signal is present"}
$$
$$
x < c \Rightarrow \text{"Signal is absent"}
$$
