[[5,2 - Decision Rules for CNNs]] $\leftarrow$ Back

---
# Signal Detection Theory
Signal detection theory, SDT, is a simple model of two-choice tasks.
- SDT is used to make decisions when noise interferes with an actual signal.

SDT states that behaviour is a function of...
1) Task ability (sensitivity).
	- How good our perception is.
2) Response bias
	- Placements of decision thresholds.

SDT is often fitted to data to estimate sensitivity and response bias.

# Relationship between SDT and ML
SDT can be thought of as way to measure how good performance is.
- Measurement is independent of bias.
- Can do the same in machine learning, using F1 scores.

Both SDT and F1 scores try to estimate performance.

SDT, like ML, produces a confusion matrix.

# Performing SDT
SDT produces a graph looking like this:

![[Pasted image 20260207160911.png]]

#### x-axis represents...
neural firing due to signal.
- Neuron activity is not directly measured, it is statistically inferred.

Let...
- $TP$ denote true positives: signal was reported when it was actually ocurring.
- $FP$ denote false positives: signal was reported when it was not occurring.

#### y-axis represents...
probability density
- Can be used to calculate the probability of a neuronal activity being at level x via integration.

Two types of curve are produced via SDT.
![[Pasted image 20260207162141.png]]
- Target absent trials curve.
	- Trials where signal was NOT present.
- Target present trials curve
	- Trials where signal WAS present.

## Target absent Trials
When no stimulus is presented, neural firing is usually low.
- Sometimes, by chance or due to noise, neural firing can be quite high or quite low despite no stimulus being shown.
![[Pasted image 20260207162430.png]]

## Target present Trials
When stimulus is shown, neural firing is usually high
- Sometimes, by chance or due to noise, neural firing can be quite high or quite low despite no stimulus being shown.
![[Pasted image 20260207162533.png]]

## All Trials
Firing is higher when a target is present than absent.
- Still expect variability trial-by-trial

![[Pasted image 20260207163148.png]]

Sensitivity, $d'$, denotes far apart the distributions are or how much they overlap.
- $d' \rightarrow \infty$, neural firing is more discriminate, research participant is better at task. 

Let...
- $present$ denote target present trial distribution.
- $absent$ denote target absent trial distribution.

$$
d' = \sqrt{\sigma_{present}^2 + \sigma_{absent}^2}
$$
