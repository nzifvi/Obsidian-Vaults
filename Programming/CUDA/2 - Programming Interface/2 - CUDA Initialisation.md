[[1 - CUDA Runtime]] <- Back
[[3,1 - Allocating Memory to Devices]] <- Next

---
## CUDA Initialisation
As of CUDA 12.0, ```cudaInitDevice()``` and ```cudaSetDevice()``` are functions which initialise the CUDA runtime and the primary context of the specified device.

If these 2 functions are not explicitly called, CUDA runtime will call them itself and use device 0 to self-initialise.

CUDA runtime creates a CUDA context for each device in a system.