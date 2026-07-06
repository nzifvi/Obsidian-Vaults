[[1 - What is Plasticity]] $\leftarrow$ Back

---
# What is Synaptic Plasticity
Synaptic plasticity is when the strength, aka weight, of a synapse between a pre-synaptic and post-synaptic neuron changes.
- Synaptic weight, $w_{i, j}$, between pre-synaptic neuron $j$ and post-synaptic neuron $i$ is altered based on activity. 


Key mechanisms of synaptic plasticity are:
1) Long-term potentiation (LTP)
2) Long-term depression (LTD)
3) Spike-timing-dependent plasticity (STDP)

## Calcium Control Hypothesis
Calcium control hypothesis: the concentration of calcium, in post-synaptic dendrite, controls the magnitude and variant of long-term synaptic plasticity.
- Let $\ohm(c)$ denote the direction of plasticity given the concentration of calcium c.
	- Two thresholds:
		1) Depression: $\theta_{d}$
		2) Potentiation: $\theta_{p}$
$$
\exists\theta_{d}, \theta{p} |\theta_{d} < \theta{p}
$$
$$
\ohm(c) = \begin{cases}
c < \theta_{d} \Rightarrow \text{baseline}\\
\theta_{d} \leq c < \theta_{p} \Rightarrow LTD\\
c \geq \theta_{p} \Rightarrow LTP
\end{cases}
$$

# Long-term Potentiation (LTP)
LTP = biological implementation of Hebbian learning at synapses.
- LTP is the sustained, hours-to-days long increase in synaptic strength that occurs when pre-and-postsynaptic neurons have correlated firing.

LTP results in a sustained increase in synaptic strength.

LTP occurs in 2 temporal phases: early-phase LTP and late-phase LTP.
- E-LTP lasts approx. 60 minutes.
- L-LTP lasts hours to days and produces structural changes in the dendrite of the post-synaptic neuron.
# Long-term Depression (LTD)
LTD is the inverse of LTP.
- It is the sustained DECREASE of synaptic weight.
- LTD is equally as important as LTP for learning.
	- Without LTD, synaptic weights can only ever increase: resulting in saturation.

