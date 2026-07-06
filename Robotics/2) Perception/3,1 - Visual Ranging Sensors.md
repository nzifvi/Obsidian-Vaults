[[3 - Mobile Robot Sensors]] $\leftarrow$ Back

---
# What is Visual Ranging Sensors
Range sensing is important for mobile robotics. It...
1) Is a basic input for proper obstacle avoidance.
2) Can be used to build environment models.

Other sensors (ultrasonic, laser, lidar) provide depth estimates. Visual sensors can still be used for this.
- Challenge: visual images make range finding difficult. They collapse a 3D world into a 2D image plane.
- This discards depth information.

Depth information can be reconstructed.
- Requires big assumptions about size of object and their colour and reflectance.
- Such assumptions are rarely possible in the real world.
- Without the assumptions. A single visual image is NOT ENOUGH to recover depth information.

2 solutions, to recover depth information reliably, exist:
1) Recover depth by looking at MULTIPLE images.
2) Create different images, without changing view point, by changing camera geometry.
	- Known as DEPTH FROM FOCUS.

# Depth from Focus
Depth from focus techniques use the fact that properties of an image are an output of 2 functions.
1) Image properties are a function of scene.
2) Image properties are a function of CAMERA GEOMETRY.

By manipulating camera geometry, depth information can be recovered.

Let...
- $d$ denote the distance between an object and the lens
- $e$ denote the distance from the lens to the focal point.
- $f$ denote the focal length of the lens

$$
\frac{1}{f}=\frac{1}{d}+\frac{1}{e}
$$
![[Pasted image 20260629105223.png]]
