[[3 - Joint Motion from Phase Oscillator]] $\leftarrow$ Back

---
# What are Coupled Oscillators?
Coupled oscillators are oscillators where their behaviour depends on the state of ANOTHER oscillator.
- Single oscillators provide rhythm. Coupled oscillators allow for coordination between oscillators.

# Coupled Phase Oscillator Model
Suppose oscillator i and j are coupled.
- To update oscillator i, from the coupled oscillator, do...
$$
\frac{d\phi_i(t+1)}{dt}=\omega_i + \sum_j\biggr[k_{ij}sin(\phi_j(t)-\phi_i(t)-\psi_{ij})\biggr]$$
Terms of coupled oscillator:
- $\omega_i$ - natural frequency of $i^{th}$ oscillator.

- $k_{ij}$ - coupling strength.
	- The larger the coupling strength, the higher influence oscillator j has on oscillator i.

- $\psi_{ij}$ - desired phase difference.
	- The desired phase difference is used to control the coordination pattern.
	- Controls how much out of phase oscillator i should be relative to oscillator j.

$$
\psi_{ij}=\phi_{j}(t)-\phi_i(t)
$$
Suppose an alternating gait is desired...
- Oscillator i should be 90 degrees out of phase from oscillator j...
$$
\phi_j(t) - \phi_i(t) = \pi \Rightarrow \psi_{ij}=\pi
$$

To update $i^{th}$ joint angle, based on it's coupled phase oscillator i, you must...
$$
\frac{d\phi_i(t+1)}{dt}=\omega_i+\sum_{j\in J}\biggr[k_{ij}sin(\phi_i(t)-\phi_j(t)-\psi_{ij})\biggr]
$$
$$
\phi_i(t+1)=\int\biggr[\frac{d\phi_{i}(t+1)}{dt}\biggr]dt
$$
$$
\theta_i(t+1)=Asin(\phi_i(t+1) + \mathcal{Y})
$$
- Can integrate phase velocity derivative, $\frac{d\phi_i(t+1)}{dt}$, using:
	1) Forward Euler.
	2) Symplectic Euler.
	3) RK4 (very accurate).

# Integrating: Forward Euler
Forward Euler states:
$$
x_{n+1}=x_n+f(x_n)\Delta t
$$
Let...
- $x_n=\phi_i(t)$
$$
x_n=\phi_i(t) \Rightarrow x_{n+1}=\phi_i(t+1)
$$
- $f(x_n) = f(\phi_i(t))$
$$
f(\phi_i(t))= \omega_i+\sum_{j \in J}\biggr[k_{ij}sin\biggr(\phi_i(t)-\phi_j(t)-\psi_{ij}\biggr)\biggr]
$$
$$
\phi_i(t+1)=\phi_i(t)+f(\phi_i(t))\Delta t
$$
Giving...
- An approximate antiderivative that can be used to produce the approximate joint angle.
$$
\theta_i(t+1) \approx Asin\biggr(\phi_i(t+1) + \mathcal{Y}\biggr)
$$
# Integrating: Symplectic Euler

# Integrating: RK4
RK4 samples slope multiple times, sampling:
- Slope at beginning.
- Two times at midpoint of slope.
- Slope at end.

RK4 then averages the samples: reducing the numerical approx. error.
- Produces more accurate approximate antiderivative than Forward and Symplectic Euler.

Produce k samples:

$$
k_1=f(x_n)
$$
$$
k_2=f(x_n+\frac{\Delta t}{2}k1)
$$
$$
k_3=f(x_n+\frac{\Delta t}{2}k_2)
$$
$$
k_4 = f(x_n+ k_3\Delta t)
$$
$$
x_{n+1}=x_n + \frac{\Delta t}{6}\biggr(k_1+2(k_2+k_3)+k_4\biggr)
$$