[[2,1 - Time Series, Phase Plane]] $\leftarrow$ Back
[[3 - Uses for RNNs]] $\leftarrow$ Next

---

# Cyclic Behaviour of RNNs
RNNs have a cyclic behaviour, both in time series and phase plane.
- Their dynamics oscillate indefinitely whilst the RNN is running. 

![[Pasted image 20260204214449.png]]

![[Pasted image 20260205104222.png]]
## Phase Plot
A phase plot has one axis being the activations of one neuron whilst the other axis is the activations of another neuron.
$$
\vec{y}(t)=\begin{bmatrix}y_1(t)\\...\\y_N(t)\end{bmatrix}
$$
Each ordinate has corresponding time indices.
- Consider a point in time p...
$$
\biggr(y_i(p), y_j(p)\biggr)
$$

# Complex Cycles or Chaotic Behaviour
Term chaos, for RNNs, refers to sensitivity of the starting state of an RNN.
- Chaos leads to colourful and complicated trajectories ?
- Chaos also implies that it is impossible to predict long-term and control an RNN (NOT TRUE).

