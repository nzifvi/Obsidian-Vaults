
---
# What is the Fourier Signal Model?
Fourier Analysis allows for a time-domain model to be built.
- Given a DFT's result, $X[n]$, a time-domain model can be made.
- Fourier signal model rewrites IDFT as a sum of real cosines.
	- Keeps frequencies which only matter.

Given DFT coefficients...
$$
X[0], X[1],...,X[n-1]
$$
An explicit time-domain signal model...
$$
x(t)=\frac{1}{n}\sum_{k=0}^{n-1}\biggr[|X[k]|cos\biggr(\frac{2\pi k t}{n \Delta t} + \phi_k\biggr)\biggr]
$$
Where...
- $\phi_k$ is the phase shift of the term.
- $|X[k]|$ is the amplitude of the term.
- $\Delta t$ is the sampling interval, a unit of time, between samples.
$$
t_j = j \cdot \Delta t \Rightarrow j = \frac{t_j}{\Delta t}
$$
To solve the amplitude, $|X[k]|$,...
$$
X[k] = a_k+ib_k
$$
- $a_k = Re(X[k])$
- $b_k = Im(X[k])$
The amplitude is equal to the magnitude of the complex number
$$
|X[k]| = \sqrt{a_{k}^{2}+b_{k}^{2}}
$$


To solve for $phi_k$...
$$
X[k]=DFT[k]=a_k + ib_k
$$
- $a_k = Re(X[k])$
- $b_k = Im(X[k])$
To solve $phi_k$, the angle of the complex number...
$$
\phi_k = arctan\biggr(\frac{b_k}{a_k}\biggr)
$$
