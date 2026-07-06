[[2 - Measuring Sensor Performance]] $\leftarrow$ Back

---
# 1) Wheel/Motor Sensors
Wheel/motor sensors are proprioceptive sensors which measure the internal state of the mobile robot.

## 1.1) Optical Encoders
Optical incremental encoders are used to measure the angular velocity and position of a motor at the shaft of a wheel.

Encoders are used to control the position/angular velocity of the motors.

As encoders are proprioceptive, any estimations of positions are best in egocentric frame.
- Any allocentric position prediction requires significant corrections.
# 2) Heading Sensors
Heading sensors can be either:
1) Proprioceptive
	- Gyroscope
	- Inclinometer
2) Exteroceptive
	- Compass

Heading sensors are used to determine a robot's orientation and bearing.

Heading sensors, in combination with information about the robot's velocity, can integrate the movement to a position estimate.
- This is known as dead reckoning.
## 2.1) Compasses
Compasses determine an allocentric heading using the direction of a magnetic field. Two most common compasses are:
1) Hall effect compass
2) Flux gate compass

### 2.1.1) Hall Effect Compass

### 2.1.2) Flux Gate compass

### 2.1.3) Compass Weaknesses
Compasses have decreased accuracy when the magnetic field of the Earth is disturbed by...
1) Other magnetic objects.
2) Man-made structures.

Compasses have decreased accuracy when vibrated.

## 2.2) Gyroscopes
Gyroscopes are heading sensors which preserve their orientation to a fixed reference-frame.
- Provide an absolute heading measure of a robot.

2 categories of gyroscopes exist:
1) Mechanical gyroscopes
2) Optical gyroscopes

### 2.2.1) Mechanical Gyroscopes
Mechanical gyroscopes use a fast spinning rotor in it's core to generate an angular momentum.
- If rotating a spinning wheel, about the y-axis, you a counteractive force will be exerted on the x-axis.
- The counteractive force keeps the gyroscope inertially stable.

![[Pasted image 20260629102258.png]]

Let...
- $\tau$ denote the reactive force.
- $||\vec{\omega}||$ denote the magnitude of the angular velocity
- $I$ denote the inertia of the wheel.
- $\Omega$ denote the precession speed

The reactive force, $\tau$, is equal to...
$$
\tau = I||\vec{\omega}||\Omega
$$
Despite the inner and outer gimbal being mostly separated, the wheel bearings still connect them both to the wheel.
- This introduces friction
- The friction causes a small accumulating error over time.
### 2.2.2) Optical Gyroscopes
Optical gyroscopes use 2 monochromatic light beams emitted from the same source.
- Speed of light is constant. Any differences in arrival time are due to geometric differences.
- No moving mechanical parts.


# Ground-based Beacons