[[1 - Intro to CPGs]] $\leftarrow$ Back
[[2,2 - Limit Cycles]] $\leftarrow$ Next

---
# What are Oscillators
Oscillators is a system which produces a repeating, rhythmic output over time.

Oscillators have the following as properties:
1) Repetition & Periodicity 
2) Self-sustaining
3) Stable or Controllable Amplitude & Frequency

## 1) Repetition & Periodicity 
The system will repeat it's behaviour, over time, in a predictable cycle.
- Any point of the cycle will repeat after the period of the wave.

## 2) Self-sustaining
A system has a STABLE LIMIT CYCLE.

A limit cycle is a __closed trajectory__ in state space of a system that is stable.

A limit cycle has...
1) A closed loop.
	- System eventually returns to same state after each cycle.

2) Attraction.
	- If system is nudged off point, it returns back to the limit cycle's pattern.
	- Limit cycles enable a oscillator to resist disturbances and continue pattern.

3) Independence from system's initial state.
	- Independence from system's initial state allows system to not have perfect starting conditions.
	- Regardless of initial state, system settles into limit cycle.

## 3) Stable of Controllable Amplitude & Frequency

4) Repetition/Periodicity
	- Repeats behaviour cyclically.
	- Examples: sine wave, swing of leg.

5) Self-sustaining.
	- Some oscillators require energy input to keep going.
	- Biological CPGs are self-sustaining rhythmic oscillators.

6) Stable or controllable amplitude & frequency.
	- If system is disturbed, a stable oscillator will eventually return to it's rhythm (called a limit cycle.)


The general form of an Oscillator, $\dot{x}(t)$, over t time...
$$
\dot{x}(t) = F(x)
$$
where...
- x is the state of the system.
- F(x) is a function which produces a repeating trajectory in state space.

# Types of Oscillators
Various types of oscillators exist. Each with a specific reason to be used.
- Different oscillators can model different phenomena. 

Some types are:
- Simple Harmonic Oscillator.
- Damped + Driven Oscillator.
- Van der Pol Oscillators.
- Phase Oscillator. 
- Hopf Oscillator. 

## Simple Harmonic Oscillator (SHO)
$$
\dot x(t)= Asin(\omega t+\phi) \begin{cases}x=\omega t + \phi\\F(x)=Asin(x)\end{cases}
$$
Variables of SHO model:
- $A$ - amplitude.
	- Controls the value of the minima and maximas of the cyclic wave.
- $\omega$ - frequency
	- Controls how fast the oscillation occurs.
- $\phi$ - phase
	- Controls where oscillation begins in limit cycle.

SHOs have...
1) Perfect periodicity 
	- Motion repeats every T.
$$
T= \frac{2\pi}{\omega}
$$
2) Energy is conserved.
	- Because energy swaps between potential to kinetic energy repeatedly, oscillation occurs is forever.

3) It is linear.

## 1) Damped Harmonic Oscillator
$$
m\frac{d^2x(t)}{dt^2}+b\frac{dx(t)}{dt}+kx(t)=0
$$
Dividing by m turns the equation into...
$$
\frac{d^2x(t)}{dt^2}+2\zeta \omega \frac{dx(t)}{dt}+\omega^2x(t)=0
$$
Where...
- $\omega$, the frequency, is equal to...
$$
\omega = \sqrt{\frac{k}{m}}
$$
- $2\zeta \omega = \frac{b}{m}$
	- b is the damping coefficient.
	- dividing b by m produces the above coefficient.

Damping removes energy from the system.
- Instead of oscillating forever, amplitude shrinks and motion eventually stops.
If...
- $0 < \zeta < 1 \Rightarrow$ System is underdamped.
	- System oscillates but amplitude decays.
- $\zeta = 1 \Rightarrow$ System is critically damped.
	- System returns to equilibrium quickly: no oscillation occurs.
- $\zeta > 1 \Rightarrow$ System is overdamped.
	- System returns to equilibrium slowly: no oscillation occurs.

Linear oscillators DO not sustain themselves. They are NOT self-sustaining.
- Without inputs, oscillation ends: no rhythm survives.
- Biological CPGs cannot be simple damped oscillators: must be more complex.

## Van der Pol Oscillator
$$
\frac{d^2x(t)}{dt^2}-\mu(1-x(t)^2)\frac{dx(t)}{dt}+x(t)=0
$$
Variables of Van der Pol Oscillator:
- $\mu$ - controls nonlinearity and strength of self-excitation.
$$
\mu > 0
$$
	- In linear damped oscillators, the damping is constant.
	- In nonlinear damped oscillators, damping is variable: depends on time.

### Nonlinear Dampers
In a van der pol oscillator, the damping term is:
$$
-\mu(1-x(t)^2)\frac{dx(t)}{dt}
$$
Suppose $|x(t)|$ is very small such that...
$$
|x(t)|>0
$$
Then...
$$
-\mu(1-x(t)^2)\frac{dx(t)}{dt}
$$
... becomes
$$
-\mu\frac{dx(t)}{dt}
$$
Negative damping occurs: negative damping now ADDs energy back into the system.
- Small oscillations begin to form.

When $|x(t)|$ is large, oscillations begin to decrease.
- Van der Pol oscillator produces self-stabilising oscillation.

## Phase Oscillator
Phase oscillators are a special type of oscillator that model the phase, rather than position and velocity.

ASSUME:
- Amplitude is stable and fixed.
- System moves about a circle at a constant velocity.

$$
\frac{d\phi(t)}{dt}=\omega
$$
$$
\int\biggr[\omega\biggr]dt=\omega t + C
$$
Where...
- $C = \phi_0$
$$
\int\biggr[\frac{d\phi(t)}{dt}\biggr]dt=\phi(t) \Rightarrow \phi(t)=\omega t + \phi_0
$$
