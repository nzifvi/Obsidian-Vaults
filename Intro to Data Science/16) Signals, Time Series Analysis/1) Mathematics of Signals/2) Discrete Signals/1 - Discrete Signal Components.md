
---
# Discrete Signal Components
Each discrete signal, $x[n]$ will have...
1) Index Set
2) Amplitude
3) Sampling Structure

# 1) Index Set
A discrete signal has a number of indices at which a sample was taken:
$$
0\leq i<n
$$

# 2) Amplitude
The amplitude of the signal is denoted by $x[n]$ itself.

# 3) Sampling Structure
The sampling structure relates a discrete signal to a continuous domain.

## Sampling Period
The sampling period, $T_s$, is the time interval between two consecutive samples.
- Unit is typically in seconds.
- Denotes time between samples being taken.

$T_s \rightarrow 0$, discrete signal better approximates it's continuous signal equivalent.

## Sampling Frequency
The sampling frequency, $f_s$, aka sampling rate is the number of samples taken per second.
$$
f_s = \frac{1}{T_s}
$$
## Discrete Signal to Continuous Signal Relationship
Considering...
1) A continuous signal $x(t)$.
2) A discrete signal $x[n]$

Sampling the continuous signal produces a discrete signal:
$$
x[n]=x(nT_s)
$$
