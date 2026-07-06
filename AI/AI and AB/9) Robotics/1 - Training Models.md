
---
# Training Models
Models, used to operate a robot, can be trained in two different ways.
- Real-world training.
- Simulation training.

## Simulation Training
Simulation training provides a simplified method to train models before deployment to the real world.

In a simulation, any variable can be accessed.
- Near infinite stream of data to provide for training the model.

In a simulation, training time can be manipulated in various ways:
- Time per training can be sped up: allows training per session to be done faster.
- Multiple training sessions can run in parallel.
## Real-world Training
Real-world training is a lot more difficult due to multiple factors.

In the real-world, you need sensors to measure the state of something.
- To get metrics for fitness functions, sensors per desired measured object are required.

Real-world training usually requires human supervision in the event something goes wrong.
- Wires tangle.
- Robot collides into something.
- Robot gets stuck
- Robot needs repair.
- Etc.

In the real-world, you cannot accelerate time to train faster. Training is constrained by time.

### Problems with Real-World
The real-world is noisy: there are many factors which may interfere with measurements and training.
1) Weather conditions.
2) Lighting
3) Untrained Events
4) Movement isn't always straight forward.
	- Determining how far, or how, a robot moves requires sensors.
	- Sensors can be noisy. All real world measurements are noisy.
	- Kalman filter or other sensor fusion methods can help reduce noise in sensor measurements.
5) Motor control problems
	- The behaviour controlling motors can begin to behave improperly: causing motors to behave weirdly.
6) Quantifying environment models of the real world.
	- Measuring the environment and modelling it is noisy, due to doing so requiring sensors.
	- 


All of these factors can result in models, trained in simulation, poorly performing in the real-world.

All of these factors can result make training in the real-world more difficult too.
# Simulation vs. Reality
When training controllers in a simulation and then using those trained models to operate a real-world robot, a reality gap exists.
- Controls purely trained in simulation tend to fail once they control a real-world robot. 
- Reality gap is the idea that controllers trained in simulations will perform differently, in a negative way, in the real world.

For a model to behave better in the real-world, the reality gap must be crossed.

## Methods for Crossing Reality Gap

### 1) Better Simulation
By making the simulation more realistic (closer in behaviour to the real world), the reality gap is reduced.

### 2) Low Resolution Sensing
By making controllers increasingly robust to noise and variance whilst they are trained during simulation, they can be made to perform better in the real world.
- When taking measurements from sensors in simulations, they are unrealistically accurate.
- All measurements taken in the real world are done by analogue systems which introduce noise into measurements.

Controllers can be improved during simulation by...
- Applying noise to sensor measurements: mimicking how measurements are noisy.
- Applying noise to motors/actuators being used: mimicking how motors/actuators often operated at imprecise values.



