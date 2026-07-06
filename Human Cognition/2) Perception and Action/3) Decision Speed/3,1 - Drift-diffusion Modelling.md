[[2 - Reaction Time Tasks]] $\leftarrow$ Back
[[3,2 - DDM vs SDT]] $\leftarrow$ Next
 
---
# What is Drift-diffusion Modelling (DDM)
DDM models certainty of two-choice decisions over time.
- x-axis is time.
- y-axis is certainty in one decision versus another.
	- Midline exists between two regions of y-axis.

![[Pasted image 20260302113627.png]]

Let $mid$ denote the midline.
- $dx(t) > mid \Rightarrow$ more certain of choice X over choice Y.
- $dx(t) < mid \Rightarrow$ more certain of choice Y over choice X.

Certainty, $dx(t)$, will have some noise associated with it.
- Noisy evidence is integrated, over time, until a decision is made.
- Evidence, which contributes to certainty of 1 over other choice, can be anything.

DDM considers how evidence accumulates over time.


# Mathematics for DDM
$$
dx=Vdt(t)+cdW(t)
$$
Where...
- $V$ is the drift rate.
	- Represents average rate of evidence accumulation toward one decision versus another.
	- Direction of drift rate, towards a decision, represented by sign of gradient.
- $c$ is the noise strength.
- $dW(t)$ is the Weiner process (Brownian motion, noise.)

To make a decision, two boundary points exist: $\theta_1, \theta_2$
- One per choice.
- Lower decision boundaries means choices are made faster.
![[Pasted image 20260304100306.png]]

Once...
$$
dx(t) \geq \theta_i
$$
... $i^{th}$ choice is made as the boundary of certainty for said choice is crossed.

Stronger evidence (higher signal-to-noise) results in a higher drift rate.
- Gradient increases.
$$
V\rightarrow \infty, dx(t)\rightarrow\infty
$$