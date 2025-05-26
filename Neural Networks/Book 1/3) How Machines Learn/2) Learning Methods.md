---
b:
---

[[1.1) Intro of How Machines Learn]]
[[3) Error Calculation]]

---
Training = very important process for neural networks.

Two types of training exist:
1) Supervised training.
	- Provides neural network with training sets and an expected output is also provided.
2) Unsupervised training.
	- Provides neural network with a training set but NO expected output is provided.


## Unsupervised Training

Unsupervised training usually used in classification neural networks.
- Classification neural networks take input patterns, which are presented to input neurons.
- Input patterns then processed, causing one single neuron in output layer to fire.
- The neuron firing can be thought of as the classification of which group the neural input pattern belonged to.


Common application for unsupervised training = datamining.
- You have a large amount of data. It is unknown what you might be exactly looking for.
- Classification neural network can be used to classify the large amount of data into several groups.
- You do not dictate, before training, what input pattern should be part of what group.
- As the neural network trains, input patterns will fall into similar groups.
- This allows you to see which input patterns are part of common groups.

Unsupervised training = very common training method for Kohonen neural networks.


## Supervised Training

Supervised training similar to unsupervised training as, like in unsupervised training, training sets are provided to the input neurons.
- Difference between 2 = in supervised training, expected outputs are provided.

By providing expected outputs to neural network, supervised training algorithms can adjust weight matrices based on the difference between actual output and expected output.
- Over many training sessions, neural network becomes more accurate at recognising input patterns.


Multiple supervised training algorithms exist. One is called the backpropagation algorithm.
- Other ones are simulated annealing and genetic algorithms. 



