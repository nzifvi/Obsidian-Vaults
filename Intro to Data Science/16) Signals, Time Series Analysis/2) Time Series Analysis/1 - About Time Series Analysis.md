[[2 - Simple Time Series Models]] $\leftarrow$ Next

---
# What is Time Series Analysis?
A time series is a set of observations, $x_t \in X$, each recorded at a specific point in time t.
- Discrete-time series consist of a set of time points and observations made at these points in time.

$$
T=<t_0, t_1,...,t_n>
$$
$$
X=<x_{t_0}, x_{t_1},...,x_{t_n}>
$$
- Continuous-time series are when observations are made continuously over a given time interval, rather than specific points in time over a time interval.

```python
import matplotlib.pyplot as pyplot

discreteTimeSeries = [5, 4, -3, 2, 4, 5, 4, 0]
sampleTimes = [0, 1, 2, 3, 4, 5, 6, 7]
pyplot.plot(sampleTimes, discreteTimeSeries, 'o-', linewidth=1)
pyplot.xlabel("Time (hours)")
pyplot.show()
```
- Above example of a Discrete-time series.

# Objectives of Time Series Analysis
1) Drawing Inferences from time-series
- Set up hypothetical probability model to represent data.
- Estimate parameters, check how well model fits to the data.
- Use the fitted model to enhance understanding of the mechanism which produced the time series.

2) Removal of seasonal components.
3) Separation, or filtering, of noise from signals.
4) Time series models are useful for simulation studies.
	- Some problems rely on a lot of random inputs.
	- A fitted model can be used to simulate large numbers of independent sequences of inputs.
	- Model can give probability of something occurring.

