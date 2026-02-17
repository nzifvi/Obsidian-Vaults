[[4,1 - Training RNNs]] $\leftarrow$ Back

---
# What are ESMs?
ESMs are a type of RNN designed to make training RNNs easier.
- Done by using a fixed, random recurrent layer called RESERVOIR.

An ESN has three layers:
1) Input layer.
2) Reservoir layer
	- Large, fixed, sparsely connected RNN.
	- Weights are untrained.
	- Purpose of reservoir is to just "echo" (repeat) the input over time.
	- Allows for rich, complex dynamics to be created.
3) Output layer.
	- Linearly reads out the reservoir state.

ONLY the output layer weights are trained: via linear regression normally.