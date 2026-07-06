
---
# What is PID
PID controllers are a feedback control loop which continuously corrects the output of a system to match a desired target. 
- Achieves this using three terms: proportional, integral, and derivative.
- Each term handles a part of an accumulated error.

Let...
- $r(t)$ denote the desired target at time t.
- $y(t)$ denote the measured output at time t.
- $e(t)$ the error at time t.
$$
e(t)=r(t)-y(t)
$$

The controller output at time t, $u(t)$, is equal to...
$$
u(t) = K_pe(t)+K_i  \int_{0}^{t}e(t)dt+ K_d \frac{de(t)}{dt}
$$
# 3 Terms
## Proportional
$$
K_pe(t)
$$
Proportional term reacts to the current error.
- Acts as a form of error correction for the current observed error.

As $K_p \rightarrow \infty$, system responds to errors more aggressively.
- High $K_p$ causes oscillation.

Proportional control will normally leave a "steady-state error", known as offset.
- Steady-state error, over time, results in accumulating error.
- Since as $e(t) \rightarrow 0$, the correction also approaches 0.

## Integral
$$
K_i \int_{0}^{t}e(t)d(t)
$$
Integral term accumulates error over time.
- If robot is consistently drifting, integral term grows and applies an increasing correction.

Integral term is used to reduce steady-state error caused by proportional control.

## Derivative
The derivative reacts to the rate of change in the error over time.
- Acts as a damping: looks at rate of error change and attempts to dampen large rates of error.
- If the error rate is small, derivative provides negative correction: preventing overshoot due to attempting to correct error.
$$
K_d\frac{de(t)}{dt}
$$
# Discretised PID
The integral and derivative terms of a PID cannot be exactly calculated.
- Must be discretised.

An error, $e[k]$, is calculated with a frequency of $T Hz$  
 
## Discretised Integral
Two discrete versions of the integral exist:
1) Riemann Sum
2) Recursive Form

### 1) Riemann Sum
$$
K_{i}T\sum_{j=0}^{k}e[k]
$$
Issues with Riemann Sum:
1) In code, must store the whole error history: memory intensive.


### 2) Recursive
The recursive variant of the discrete integral means that only the prior integral is stored.
- Less memory intensive (GOOD)
- Less accurate integral (BAD)
$$
f(k) = f(k-1) + K_iTe[k]
$$

MUST store $f(k-1)$ as a runtime variable.

### 3) Window
Rather than storing a whole history of gradients, a queue data structure can be used.
- Store up to n errors.
- Once n errors stored, dequeue before enqueueing new errors.
- That way, the most recent n errors are stored.

```pseudocode
queue <- queue.BUILD()

while robot is running:
	e = r - t
	if queue.size() > 5 then:
		queue.dequeue()
		queue.enqueue(e)
	else:
		queue.enqueue(e)
```

Then take the Riemann sum of the queue, which stores a recent history, rather than an overall history
- Back of the queue will ALWAYS be $e[k]$
$$
Queue_{Length} = k
$$

## Discretised Derivative
To calculate the derivative, slope of the chord approximation.
- Only must store the previous error.
- No need to store previous time. EVERY sample will have a difference of T between them.

$$
\frac{de(t)}{dt} \approx \frac{e[k]-e[k-1]}{T}
$$
