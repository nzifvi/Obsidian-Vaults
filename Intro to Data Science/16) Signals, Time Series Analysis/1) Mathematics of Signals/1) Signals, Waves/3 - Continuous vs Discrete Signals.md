[[2 - Periodicity and Waves]] $\leftarrow$ Back
[[4 - Similarity between Signals]] $\leftarrow$ Next

---
# What is a Continuous Signal?
A signal, $x(t)$, is a continuous-time signal if:
$$
x: \mathbb{R} \rightarrow \mathbb{R}
$$
Meaning...
- Time t can be ANY real number.
$$
t\in\mathbb{R}
$$
- Signal has a value at every instant t.

```python
import numpy
import matplotlib.pyplot as pyplot

amplitude = 1
frequency = 2
phi = 0
endTime = 2
sampleRate = 100

time = numpy.linspace(0, endTime, int(sampleRate*endTime), endpoint=False)
y = amplitude * numpy.sin(2*numpy.pi*frequency*time + phi)

pyplot.figure(figsize=(8,4))
pyplot.plot(time, y)
pyplot.xlabel("Time t in (seconds)")
pyplot.ylabel("x(t)")
pyplot.grid(True)
pyplot.show()
```
# What is a Discrete Signal?
A signal, $x[n]$, is a discrete-time signal if:
$$
x:\mathbb{Z} \rightarrow \mathbb{R}
$$
Meaning...
- The independent variable, n, is an integer index n.
- Signal ONLY has values at those integer indices.

Discrete signals are signals generated via measurements at points in time. Discrete signals can be thought of as a sequence of numbers.

In a discrete signal:
- Each number corresponds to one measurement: a sample.
- Nothing is defined between samples.

```python
import numpy
import matplotlib.pyplot as pyplot

samplingFrequency = 100
duration = 1
fundamentalFrequency = 5

samplingPoints = numpy.arange(0, duration*samplingFrequency)
time = samplingPoints / samplingFrequency

x = numpy.sin(2* numpy.pi * fundamentalFrequency * time)

pyplot.stem(samplingPoints, x, basefmt=" ")
pyplot.xlabel("indices")
pyplot.ylabel("x[n]")
pyplot.show()
```
