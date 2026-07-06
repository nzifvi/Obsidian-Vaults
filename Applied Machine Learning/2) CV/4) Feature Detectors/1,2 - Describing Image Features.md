[[1,1 - Problems with Pixels]] $\leftarrow$ Back
[[1,3 - Geometric & Photometric Transformations]] $\leftarrow$ Next

---
# Describing Image Features
Describing image contents should be done in a way which has a degree of invariance to changes in...
- Contrast.
- Position
- Scale
- Etc

Instead of describing every pixel, specific key points of an image are detected.

Describing image features has a lot of applications:
- Tracking moving objects in a sequence of images.
- Localising face landmarks (face finding)
- Human pose detections.
- Object detection and recognition.
- 3D object reconstruction (building 3d images from many 2d images).

## Operator Repeatability 
Operator repeatability means that an operation can be used many times to produce the desired output of said operator.

## Feature Distinctiveness
Feature distinctiveness is the idea that, between images, corresponding features can be found.
- Requires some invariance to geometric and photometric differences in the two views.
