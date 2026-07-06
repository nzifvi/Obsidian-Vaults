[[1,1 -How SNNs Work]] $\leftarrow$ Back

---

$$
I(t)=\sum\biggr[w_{ij}\delta(t-t_i-d_{ij})\biggr]
$$
Where...
- $w_{ij}$ is the synaptic weight between neuron i and j.
- $d_{ij}$ is the delay between neuron i and j.
- $t_i$ is the spike time.

# Types of Architectures
# Feedforward SNN
In a feedforward SNN...

Layers:
Input $\rightarrow$ Hidden Layer(s) $\rightarrow$ Output

Spikes propagate forward only: there is no recurrence.
- NO feedback.

### Advantages of Feedforward SNNs
1) Simple and easy to simulate.
2) Good for classification & perception tasks.

### Disadvantages of Feedforward SNNs
1) Cannot maintain memory of past inputs.

## Uses of Feedforward SNNs
1) Event-based image classification.
2) Terrain recognition from LiDAR or event camera spikes.

# Recurrent SNN
Recurrent SNNs, RSNNs, have recurrent layers. In recurrent layers, layers of neurons may have feedback connections.

Types of layers:
- Input.
- Recurrent Layer(s).
- Output.

The input layer encodes temporal or spatial information into spikes.
- Encoding can be rate-based, temporal, or population based.

# Reservoir / Liquid State Machines

# Convolutional SNNs

# Specialised Architectures

## Spiking Wavefront Planner

## Spiking RNN for RL

## Hierarchical SNNs