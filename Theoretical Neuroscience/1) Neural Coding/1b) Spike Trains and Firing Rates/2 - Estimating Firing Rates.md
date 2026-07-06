
---
# Estimate Firing Rates
The activity of a neuron, at time t, depends on the behaviour of a stimulus over a period of time.
- Period of time normally starts a few hundred $ms$ prior to t and ends tens of milliseconds before t.

Reverse correlation methods can be used to create a more accurate model which includes...
- Effects of stimulus over period of time.


Basic problem: construct estimate, $r_{est}(t)$, of firing rate, $r(t)$, evoked by a stimulus $s(t)$. Basic idea is to assume firing rate, at any given time, can be expressed as weighted sum of values taken by stimulus at earlier times.
- Since time is continuous variable, sum is expressed as integral.

$$
r_{est}(t) = r_0 + \int_{0}^{\infty}D(\tau)s(t - \tau) d\tau
$$
- NOTE: must quantise if needing to do with computer.
- Term $r_0$ accounts for background firing that occurs when $s = 0$
- $D(\tau)$ is a weighting factor determining how strongly, and with what sign, the value of the stimulus is at time $t-\tau$.

Sensory systems tend to adapt to absolute intensity of stimulus.
- Easier to account for responses to fluctuations of stimuli around some mean background level.
- Therefore: assume assume stimulus parameter, $s(t)$, has been defined with the mean stimulus intensity value subtracted.

$$
r_{est}(t) = r_0 + \sum_{i=1}^n\biggr[\int D_i(t_1,...,t_i)\prod_{j=1}^{i}s(t-\tau_j) \prod_{j=1}^i d\tau_j\biggr]
$$
