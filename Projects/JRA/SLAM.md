
---
# What is SLAM
Simultaneous Localisation and Mapping, SLAM, = fundamental technique for enabling autonomous robots to create a map of an environment and determine their own position within said environment.

Challenge for SLAM: localisation and mapping are interdependent.
- To locate itself, robot needs a map.
- To build a map, robot needs to know where it is.

SLAM solves interdependent tasks by combining them into a single process.
- Allows the two interdependent tasks to be performed simultaneously.
- SLAM is performed dynamically as the robot explores environment.

SLAM provides greater localisation accuracy.
- Useful in environments where GPS signals are weak or non-existent.

# SLAM Structure
## Frontend
Frontend receives raw data from sensors, processes it, and extracts features from environment.

Data acquisition can be achieved by multiple types of sensors:
- Monocular.
- Stereo.
- RGB-D.
- LiDAR.
- Radars.
- Ultrasound.
- IMUs.

Final step of frontend structure is the making of an odometry estimate.
- Odometry estimate calculates relative movement of sensors, between consecutive frames, enabling localisation within a map.

Multiple approaches exist to frontend SLAM:
- LiDAR Odometry

### LiDAR Odometry
LiDAR Odometry relies on LiDAR sensors to obtain 3d points in LiDAR cloud which models the environment.
- Can be combined with IMUs for greater accuracy.
## Backend
Backend receives observations processed by frontend and then globally optimises the map and sensor trajectory.
- Uses mathematical techniques to...
	1) Minimise accumulated errors over time.
	2) Correct drifts.
	3) Ensure map and location consistency.

Main functions of backend are...
1) Graph optimisation.
	- Positions of sensors are estimated.
	- Visual landmarks adjusted to minimise overall error.
2) Error minimisation
	- Reduces uncertainty in estimates.

Backend also performs loop closure detection.
- System identifies a return to previously mapped location