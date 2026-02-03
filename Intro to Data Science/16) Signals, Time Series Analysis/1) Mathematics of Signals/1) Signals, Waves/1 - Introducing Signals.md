[[2 - Periodicity and Waves]] $\leftarrow$ Next

---
# 1) What are Signals?
Signals are a way of conveying information.
- Signals, abstractly, are how something changes over something time or frequency.

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

A signal, $x(t)$, over time $t$ represents a quantity, or something else, at every point in time t.
- If you want to know the value of something at time a you plug a into $x(a)$

# 2) Math Notation
$x(t)$ denotes a CONTINUOUS-TIME SIGNAL.
- $t \in \mathbb{R}| -\infty < t < \infty$ 
- Interpreted as "signal x at time t"

$x[n]$ denotes a DISCRETE-TIME SIGNAL.
- $t\in \mathbb{Z}|-\infty<t<\infty$
- Interpreted as "n$^{th}$ sample of signal x" 

$x(t)$ refers to an INPUT signal and $y(t)$ refers to an OUTPUT signal.

t ALWAYS refers to a unit of time.
- standard unit of t is usually seconds, can be something else however.


Considering t = 0...

$$
t<0 \Rightarrow x(t) = 0
$$
- If t equals zero, let x(t) = 0. This is because anything less than 0 is before the signal started to be recorded.

Considering n = 0...
$$
n < 0 \Rightarrow x[n]= 0
$$
- For same reason as why x(t) = 0.

Angles, $\pi$ and $\phi$, are, by standard, recorded in radians.
