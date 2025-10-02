[[2 - CUDA Initialisation]] <- Back
[[3,2 Copying Memory between Host and Device]]

---
## Allocating Memory to Devices
Recall from Heterogeneous Programming section:
- A device and host has separate memory regions in dynamic RAM.

Kernels operate using device memory, so CUDA runtime provides functions to...
1) Allocate memory to and deallocate memory from a device.
2) Copy device memory.
3) Transfer data between host memory and device memory.

Device memory can be allocated as linear memory or as CUDA arrays.
- CUDA arrays are memory layouts optimised for texture fetching (covered later).

- Linear memory is allocated in single, unified addresses.

## Allocating and Deallocating Linear Memory to Device
Linear memory is normally allocated using ```cudaMalloc()``` and then freed using ```cudaFree()``` functions.

```c++
int arraySize = n;
size_t = arraySize * sizeof(dataTypeOfArray);

// first, allocate memory for data structures in host memory
float* ptrHostVectorA = new float[arraySize];
float* ptrHostVectorB = new float[arraySize];
float* ptrHostVectorC = new float[arraySize];

// suppose all vectors are initialised...

// Allocate memory for data structures in device memory.
float* ptrDeviceVectorA;
float* ptrDeviceVectorB;
float* ptrDeviceVectorC;

cuda::cudaMalloc(&ptrDeviceVectorA, arraySize);
cuda::cudaMalloc(&ptrDeviceVectorB, arraySize);
cuda::cudaMalloc(&ptrDeviceVectorC, arraySize)
```

Deallocation of device memory previously allocated via cudaMalloc() is done via cudaFree().

```c++
cudaFree(ptrDeviceVectorA);
cudaFree(ptrDeviceVectorB);
cudaFree(ptrDeviceVectorC);
```

