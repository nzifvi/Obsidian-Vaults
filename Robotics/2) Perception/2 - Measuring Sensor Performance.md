[[1 - Sensor Classification]] $\leftarrow$ Back
[[3 - Mobile Robot Sensors]] $\leftarrow$ Next

---
# Basic Sensor Response Rating
Some sensor properties can be rated quantitatively in a lab setting.
- LAB RATINGS WILL BE BEST CASE SCENARIO: NEVER ACCURATELY REFLECT REAL-WORLD OPERATION ACCURACY

## Dynamic Range
Dynamic range is used to measure the spread between the lower and upper limits of input values to the sensor during normal sensor operation.
- Measured in decibels due to the raw ratio being unwieldy

Let...
- $a_{min}$ denote the lower input bound
- $a_{max}$ denote the upper input bound.

$$
f(a_{min}, a_{max}) = 10\text{log}\biggr(\frac{a_{max}}{a_{min}}\bigg)
$$
NOTE: the unit of $a_{max}$ and $a_{min}$ must be the same

## Resolution
Resolution is the MINIMUM difference, between 2 values, a sensor can detect
- Sensor's resolution is often the lower limit of dynamic range.
- ABOVE NOT TRUE FOR DIGITAL SENSORS.

## Linearity
Linearity is a behavioural measure of the sensor's output signal as the input signal varies

A linear response means that, if 2 inputs, $x_1$ and $x_2$, result in two outputs $f(x_1)$ and $f(x_2)$ then for any input values a, b...
$$
f(ax_1+bx_2)=af(x_1)+bf(x_2)
$$
If linear, this means that the plot of the sensor's output response dependent on input values is a straight line.

## Frequency
Frequency is a measure of the speed a sensor can provide a stream of readings.
- Measured as the number of measurements per second.
- Unit is Herts (Hz)
# In-situ Sensor Performance
## Sensitivity
Sensitivity is a measure of how much an incremental change in an input signal can impact the output signal.

Sensitivity measured as ratio of output change to input change.

Exteroceptive sensors are often subject to undesirable sensitivity.
- Results in poor performance.

## Cross-sensitivity
Cross-sensitivity is sensitivity to environmental parameters.

## Error
The error of a sensor defined as difference between sensor's measured output and the real, true output it should be measuring.

Let...
- $y$ denote the actual output value a sensor should be reading
- $\hat{y}$ denote the output value a sensor IS reading
- $\mathcal{L}(y, \hat{y})$ be a loss function which calculates the error.

$$
\mathcal{L(y, \hat{y})} = y - \hat{y}
$$
### Systematic vs. Random Errors
2 sources of error exist:
1) Systematic error.
2) Random error.

Systematic errors are caused by factors which can potentially be modelled. Some causes are:
- Uncalibrated sensors.
- Damage to sensors.
- Etc.
Systematic errors are deterministic.

Random errors cannot be predicted. These errors can only be calculated using probabilistic methods. Some sources of random errors are:
1) Noise in sensors.
## Accuracy
Accuracy is a measurement of how a sensor's measurement corresponds to the true value it should be measuring.
- A small error results in high accuracy.
- Large error results in low accuracy.

Accuracy, a, is calculated below:
$$
a = 1-\frac{\mathcal{L(y, \hat{y})}}{y}
$$

## Precision
Precision is a measure of how reproducible a sensor's outputs are given the sensor detects the SAME THING.
- Given sensor detecting same thing, precision increases the more similar the output signals are.

Precision has no impact on the accuracy of a sensor's output.

Suppose a random error of a sensor can be defined by...
1) Mean error $\mu$
2) Std. dev $\sigma$

Precision is calculated by...
$$
\text{precision} = \frac{\text{range}}{\sigma}
$$
Where...
- $\text{range}$ denotes the range of a sensor's output values.

NOTE: only the std. dev of the error has an impact on precision.
- The mean error is proportional to the overall sensor error.
	- As mean error increases, sensor error increases.
- The mean error is inversely proportional to sensor accuracy.
	- As mean error decreases, sensor accuracy increases.

# Describing Error: Challenges of Mobile Robotics
Mobile robots depend on exteroceptive sensors.
- Exteroceptive sensors often used for central tasks of robot: acquiring information of robot's immediate environment.

Exteroceptive sensor measurements are made egocentrically (relative to robot)
- Mobile robots have an ever-changing position: their motion has significant impacts on sensor behaviour.

## Blurring Systematic and Random Error
The errors of a robot's sensors can increase due to motion or environmental factors. This blurs the lines between systematic and random errors.

Some examples of sensors which blur the lines between systematic and random errors, during operation on a mobile robot, are:
1) Sonar sensors.
	- Sonar sensor produces specular reflections: creating inaccurate distance readings.
	- Even more likely if a robot has a ring, or array, of sonar sensors in operation.
2) CCD cameras.
	- Visual interpretation, through a CCD camera, is impacted by the motion and position of a robot.
	- The camera is dependent on lighting changes, glare, and reflections.
	- These dependencies, impacted by motion and position, can create large errors in CCD camera readings.
3) MANY other sensors are subject to higher errors in readings. Always investigate possible causes of error in a sensor being used.

The cause of blurred systematic and random errors, in mobile robots, is the cross-sensitivity between the sensors, of a mobile robot, and the pose of the robot and the environment of the robot.


# Multimodal Error Distributions
A sensor's random error is characterised as a probability distribution over various output values.

Little is known about the causes of random error. Due to this, a few assumptions are made:
1) Error has a mean of 0.
	- There can be both positive and negative error values.
2) Random error is to be distributed as a Gaussian
- Above assumptions enable math principles to be applied to the problems faced by mobile robots.
- HOWEVER: remember these assumptions are often not true at all.