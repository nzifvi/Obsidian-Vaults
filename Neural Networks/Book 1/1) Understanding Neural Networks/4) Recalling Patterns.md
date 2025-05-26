---
a:
---

[[3) Hopfield Network]]

[[4.1) Deriving Weight Matrix]]

[[1.1) Intro of How Machines Learn]]

---
Section describes how a neural network is used to recall patterns.

1) Each input neuron is presented with a copy of the image.
	- If using a Hopfield Network, each neuron will be presented with a copy as all neurons are input and output neurons.


Suppose a Hopfield network is trained to detect 0101 and 1010.
- Suppose said Hopfield network is shown 0101.

![[Pasted image 20250206205928.png]]

- Each Neuron activates based upon the inputted pattern.
- In this case, Neuron 1's activation is the sum of all the weights that have a 1 in the input pattern.

Weights for N1

![[Pasted image 20250206210049.png]]

- Compare the weights with the input pattern

![[Pasted image 20250206210359.png]]

- When summing the weights, only include the indices where the input pattern has a 1 as well

n1 = -1 -1 = -2

So.... for all neurons

![[Pasted image 20250206210911.png]]

n1 = -1 + -1 = -2
n2 = 0 + 1 = 1
n3 = -1 + -1 = -2
n4 = 1 + 0 = 1

n1 = -2 (0), does not fire
n2 = 1 (1), does fire
n3 = -2 (0), does fire
n4 = 1 (1), does fire)

![[Pasted image 20250206211416.png]]

Since the outputted pattern is equivalent to the inputted pattern, the neural network has auto associated: indicating that the pattern was recognised.
- The input is confirmed to be 0101.


- Binary 1 is assigned to a neuron that has fired.
- Binary 0 is assigned to a neuron that has not fired.


- An auto association neural network, like a Hopfield network, will output the input pattern: echoing it to indicate it has been recognised.