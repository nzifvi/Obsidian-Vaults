[[1 - Introducing Signals]] $\leftarrow$ Back

---
# Periodicity
A signal, $x(t)$, is PERIODIC if there is some value, $t_0$, which means that for any t...
$$
x(t+t_0)=x(t)
$$
- $t_0$ is the FUNDAMENTAL period of signal $x(t)$.
- A period is the length of an interval which it takes for a signal to repeat. If a signal repeats, it will have the same between two points: $t_i$ and $t_i + \Delta t$

If a signal is periodic, it will repeat forever:
$$
x(t)=x(t+\Delta t) = (x + 2t_0) = ...=x(t+ n t_0)
$$
- $n \in \mathbb{Z} | 0 \leq n < \infty$

## Aperiodic Signals
An aperiodic signal is a signal which has NO period. It will never repeat itself exactly.
- Common notation for aperiodic signals lets $\Delta t = \infty$, which expresses that you need to wait forever for signal to repeat.

Many types of aperiodic signals exist:
- Random noise, like white noise, is an aperiodic signal.

Aperiodic signals are not predictable.
- Values of a aperiodic signals can be predicted.
- A signal being aperiodic only means that you never seem the same EXACT value again.

## Fundamental Frequency
Periods defined in units of time.

Sometimes, more useful to think how many times a signal repeats itself within a fixed duration of time.
- Normally 1 second.

The fundamental frequency is a measurement of how many cycles, periods, does a signal complete in 1 second.
- Frequency measured in units of Hertz (Hz)
- 1 Hz denotes a full cycle in one second

Let $f_{fundamental}$ denote fundamental frequency...
$$
f_{fundamental}=\frac{1}{t_0}
$$
- If signal $x(t)$ has a period, i.e. the signal is periodic, it's fundamental frequency is f Hz.
- If signal x(t), has NO period, i.e. the signal is aperiodic, it's fundamental frequency is 0 Hz.

The fundamental period, $t_0$, and fundamental frequency, $f_{fundamental}$, are distinguished due to 2 reasons:
1) To distinguish fundamental periods and frequencies from arbitrary times, t, and frequencies, f.
2) To demonstrate a connection between fundamental frequency and harmonics/overtones.

# Waves

## Sinusoids and Rotation
Sinusoids are well-suited for processing and analysing signals.
- The reason why sinusoids are used is to due their mathematical properties. 
- 

![[Pasted image 20260115162904.png]]

- $sin(\theta)$ is the height from the origin's vertical ordinate to the vertical ordinate of a point on the circle.
- $cos(\theta)$ is the distance from the origin's horizontal ordinate to the horizontal ordinate of a point on the circle.

When $\theta$ goes all the way to 2$\pi$, a full rotation of the circle has been completed.
- This corresponds with an entire cycle of a signal, $x(t)$, being completed.

The angle, $\theta$, is changed over time, rotating over time. Therefore the angle is a function of time.
- $\theta(t)$

## Wave Parameters
A simple wave can be modelled with the following function:
$$
x(t)=A \cdot cos(2\pi \cdot f \cdot t \cdot \phi)
$$
Where...
- A = amplitude of wave.
	- Calculated by subtracting the absolute minima from the absolute maxima of the wave.
- f = frequency of wave: how many cycles completed in 1 second.
- $\phi$ = phase offset of the wave: starting position, in radians, at time = 0.
- 
