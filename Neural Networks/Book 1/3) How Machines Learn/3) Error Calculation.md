---
b:
---

[[2) Learning Methods]] <- back
[[4) Types of Neuron Layers]] <- next

---

Error calculation = important part of any neural network.
- Applies to both supervised and unsupervised learning neural networks.
- Goal of all training algorithms is to reduce errors.
- Ways to calculate error methods for unsupervised and supervised learning algorithms exist...


## Error Calculation for Supervised Training

Error calc = important part of supervised training algorithms.
- With supervised learning algorithms, two parts of the error must be taken into consideration.
1) Error for each training set as they are being processed.
	- Aka output error.
2) Average error across EACH sample for the training set.
	- Aka Root Mean Square error.

- For each element of a training set, an output error must be calculated.

### Output Error
[[3.1) Supervised Learning Errors - Calculating Output Errors.]]

Output error = error calculation that determines how far off a neural network's output was from the ideal output for that element of the training set.

### Root Mean Square
[[3.2) Supervised Learning Errors - Calculating Root Mean Square Error]]

Once all training sets have been used, the Root Mean Square (RMS) can be calculated.
- RMS acts as global error for the ENTIRE neural network.