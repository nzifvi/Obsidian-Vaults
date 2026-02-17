[[4,1 - Training RNNs]] $\leftarrow$ Back

---
# What are ANNs?
ANNs are a type of RNN designed such that the dynamics naturally evolve towards a stable pattern.
- The stable pattern referred to as ATTRACTORS.

Attractors can represent...
- Memories.
- Pattern.
- Solutions, depending on purpose of ANN.

In an ANN, ANN's state at time t is given by a discrete signal of neuron activations:
$$
x[t]=<x_1(t), x_2(t),...,x_N(t)>
$$
- Modelled as a vector rather than sequence
$$
\vec{x}[t]= \begin{bmatrix}x_1(t)\\...\\x_N(t)\end{bmatrix}
$$

$$
x[t+1]=g\biggr(W\vec{x}[n] + \vec{\theta}\biggr)
$$
# Types of Attractors
Multiple types of attractors exist, each causing different behaviour and enabling different uses:
- More types exist than ones mentioned below
## 1) Point Attractors
Point attractors cause ANNs to settle into a singular, fixed pattern.

## 2) Cyclic Attractors
Cyclic attractors cause ANNs to settle into a repeating cycle of states.
- Good for modelling sequences, rhythmic patterns, and or cyclic signals.

## 3) Chaotic Attractors
Chaotic attractors cause ANNs to not settle. Instead, they cause complex, bounded, non-repeating dynamics.
- Good for modelling brain activity and unpredictable behaviour/events.