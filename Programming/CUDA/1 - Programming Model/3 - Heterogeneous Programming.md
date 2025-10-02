[[2 - Thread Block Clusters]] <- Back

---
## What is Heterogeneous Programming?
CUDA assumes that CUDA threads are executed on a device physically separate from the host which runs a program.
- Example: kernels are executed on GPU, rest of C++ program executed on CPU.

CUDA programming model also assumes that both the host and device maintain their own separate memory spaces in dynamic RAM, referred to as host memory and device memory.