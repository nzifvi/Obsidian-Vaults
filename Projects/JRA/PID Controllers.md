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
u(t) = K_pe(t)+K_i  \int_{0}^{t}e(\tau)d\tau + K_d \frac{de(t)}{dt}
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