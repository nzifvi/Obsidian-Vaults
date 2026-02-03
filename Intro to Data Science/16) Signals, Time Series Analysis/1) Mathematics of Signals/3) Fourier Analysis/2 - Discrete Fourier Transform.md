[[1 - What is Fourier Analysis]] $\leftarrow$ Back

---

# What is the Discrete Fourier Transform?
Given a finite discrete signal $x[n]$ such that...
$$
x[0], x[1],...x[n-1]
$$
Discrete Fourier Transform, DFT, solves how much of a sinusoidal $k^{th}$ term with a fundamental frequency of $f_{k}$ exists in the signal
- 

$$
X[k]= \sum_{j=0}^{n-1}\biggr[x[j]\cdot e^{-i2\pi\frac{k}{n}j}\biggr]
$$
## Basis Wave
The basis wave is...
$$
e^{-i2\pi \frac{k}{n}j}
$$
Using Euler's formula:
$$
e^{-i\theta}= cos(\theta) -isin(\theta)
$$
Let...
$$
\theta = 2\pi \frac{k}{n}j
$$
Therefore...
$$
e^{-i2\pi\frac{k}{n}j}=cos\biggr(2\pi\frac{k}{n}j\biggr)-isin\biggr(2\pi\frac{k}{n}j\biggr)
$$
Because each element of the finite discrete signal is multiplied by the basis wave, $X[k]$ becomes a signal of complex sinusoidal elements. 
# Transforming DFT into a solvable form
Knowing that...
$$
e^{i\theta}=cos(theta)-isin(\theta)
$$
Let...
$$
\theta=f(k,j,n) | f(k,j,n) = \frac{2\pi kj}{n}
$$
Substituting these into DFT summation formula...
$$
X[k]=\sum_{j=0}^{n-1}\biggr[x[j]\biggr(cos(f(k,j,n))-isin(f(k,j,n))\biggr)\biggr]
$$
...gives a computable version of the DFT.
# Example
Suppose...
$$
x[n] = \{1, 0, -1, 0\}
$$
- n = 4 $\Rightarrow$ n - 1 = 3

Need to solve $X[n]$
- $X[0]$
- $X[1]$
- $X[2]$
- $X[3]$

### Solving $X[0]$

### Solving $X[1]$

### Solving $X[2]$

### Solving $X[3]$
## In Python

```python
import numpy
import cmath

def computeDFTBaseWave(k:int, j:int, n:int, zeroThreshold:float = 1e-12) -> complex:
	theta = (2 * numpy.pi * k * j)/n
	baseWave = complex(numpy.cos(theta), -numpy.sin(theta))
	realTerm = baseWave.real
	imagTerm = baseWave.imag
	if abs(realTerm) < zeroThreshold:
		realTerm = 0.0
	if abs(imagTerm) < zeroThreshold:
		imagTerm = 0.0
	return complex(realTerm, imagTerm)
	
def dft(discreteSignal:list) -> list:
	dftSignal = []
	for k in range(len(discreteSignal)):
		sumOfTerms = 0j
		for j in range(len(discreteSignal)):
			sumOfTerms += discreteSignal[j] * computeDFTBaseWave(k, j, len(discreteSignal))	
		dftSignal.append(sumOfTerms)
	return dftSignal

discreteSignal = [1, 0, -1, 0]
print(dft(discreteSignal))
```





