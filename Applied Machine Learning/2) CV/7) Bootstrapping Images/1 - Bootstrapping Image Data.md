#CV #AppliedMachineLearning #Bootstrapping 

---
# 1) Bootstrapping Image Data
Bootstrapping image data consists of applying geometric and or brightness/intensity transformations.

Any geometric transformations performed to an image MUST also be performed to actual outputs if the actual outputs are points rather than classes.

# 2) Bootstrapping Geometric Transformations 
Geometric transforms such as...
- Rotations by a random amount of radians.
- Translation by a random amount of pixels.
- Scaling the image by a random amount.
... can be performed on a random image part of a set of images to bootstrap.

# 3) Bootstrapping Brightness/Intensity Transformations.