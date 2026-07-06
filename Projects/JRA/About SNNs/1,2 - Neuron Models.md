[[1,1 -How SNNs Work]] $\leftarrow$ Back

---
# Neuron Models
Neuron models define dynamics of SNN. In particular, the dynamics they define are...
- Membrane potential evolution.
- Threshold for spike generation.
- Refractory behaviour.

Neuron models also determine encoding styles.
- Rate coding, temporal coding, population coding.
- Some neuron models are suited for precise timings whilst others for more complex dynamics.

Neuron models control network behaviour.

# LIF Neurons
A Leaky Integrate-and-Fire, LIF, neuron is a model of a biological neuron.
- Integrates incoming current.
- Leaks current over time.
- Fires a spike when membrane potential rises above a threshold. 


## LIF Neuron Components
Let...
- $V(t)$ denote membrane potential at time t.
	- Increases with input, decreases over time.

- $V_{threshold}$ denote the threshold voltage.
	- $V(t) \geq V_{threshold} \Rightarrow$ Neuron fires a spike.

- $V_{reset}$ denote the reset potential.
	- Membrane potential becomes equal to $V_{reset}$ post firing, returning to baseline.

- $\tau$ denote the leak constant.
	- Controls how fast $V(t)$ decays back to resting potential.

## LIF Neuron Modelling
LIF neurons modelled via differential equation

$$
\tau\frac{dV(t)}{dt}=-V(t)+I(t)
$$
Cannot model them in continuous time, must do it discretely.

$$
V[t+\Delta t]=V[t]+\frac{\Delta t}{\tau}\biggr(-V[t]+I[t]\biggr)
$$
The output spike, $S[t+\Delta t]$, is given by...
$$
S[t+\Delta t]= \begin{cases}V[t+\Delta t]\geq V_{threshold}\Rightarrow S[t+\Delta t]=1\\V[t+\Delta t] < V_{threshold} \Rightarrow S[t+\Delta t] = 0\end{cases}
$$
If the neuron has fired, reset the membrane potential.
$$
S[t+\Delta t]=1 \Rightarrow V[t+\Delta t] \leftarrow V_{reset}
$$

# Izhikevich Neurons 
Izhikevich neuron designed to capture wide variety of firing patterns observed in real biological neurons.

Good for...
- Bursting neurons.
- Chattering neurons.
- Spike-frequency adaption.
## Izhikevich Neuron Components
Let...
- $v(t)$ denote membrane potential at time t.
- $u(t)$ denote recovery variable at time t.

## Izhikevich Neuron Modelling
Izhikevich neurons modelled with 2 differential equations:
$$
\begin{cases}\frac{dv(t)}{dt} = 0.04v(t)^2+5v(t)+140-u(t)+I(t)\\\frac{du(t)}{dt}=a\biggr(bv(t)-u(t)\biggr)\end{cases}
$$
If...
$$
v(t) \geq 30mV \Rightarrow \begin{cases}v(t)\leftarrow c\\u(t)\leftarrow u(t)+d\end{cases}
$$
Where...
- $a$ denotes the recovery time constant.
	- Controls how fast recovery variable, $u(t)$, reacts to changes in membrane potential $v(t)$

- $b$ denotes voltage recovery sensitivity.
	- Controls how strongly recovery variable, $u(t)$, responds to changes in membrane potential $v(t)$

- $c$ denotes reset membrane potential.
	- Determines the resting potential of a neuron post firing.

- $d$ denotes recovery variable, $u(t)$, jumps when a spike occurs for a neuron.
	- d controls just how much the recovery variable will spike.