
---
# What is the Inverse Discrete Fourier Transform?
Inverse Discrete Fourier Transform, IDFT, builds the signal as a sum of rotating, complex base waves.
- Given a DFT, the IDFT is equal to...
$$
x[n]=\frac{1}{n}\sum_{k=0}^{n-1}\biggr[X[k]\cdot e^{i2\pi \frac{kj}{n}}\biggr]
$$
Recall that:
$$
e^{i\theta}=cos(\theta)+isin(\theta)
$$
Let...
$$
\theta=f(k,j,n)=\frac{2\pi kj}{n}
$$
The IDFT can be rewritten as...
$$
x[n]=\frac{1}{n}\sum_{k=0}^{n-1}\biggr[X[k]\biggr(cos(f(k,j,n))+isin(f(k,j,n))\biggr)\biggr]
$$
The summation will cancel out the imaginary part of the complex numbers from the DFT, leaving only a sequence of real numbers.
# Example

## In Python

```python
import cmath
import numpy

def thetaTransform(k:int, j:int, n:int) -> float:
	return (2*numpy.pi*k*j)/n

def computeIDFTBaseWave(k:int, j:int, n:int, zeroThreshold:float = 1e-12) -> complex:
	baseWave = complex(numpy.cos(thetaTransform(k,j,n)), numpy.sin(thetaTransform(k,j,n)))
	realTerm = baseWave.real
	imagTerm = baseWave.imag
	
	if abs(realTerm) < zeroThreshold:
		realTerm = 0.0
	if abs(imagTerm) < zeroThreshold:
		imagTerm = 0.0
		
	return complex(realTerm, imagTerm)

def idft(dftSignal:list) -> list:
	idftSignal = []
	n = len(dftSignal)
	for j in range(n):
		sumOfTerms = 0j
		for k in range(n):
			sumOfTerms += dftSignal[k] * computeIDFTBaseWave(k, j, n)
		idftSignal.append(sumOfTerms.real)
	return [x / n for x in idftSignal]
	
dftSignal = [0, 2, 0, 2]
print(idft(dftSignal))
```
