
---
## What is CUDA?
CUDA is a parallel computing platform & programming model.
- Developed by NVIDIA.
- Allows for large increases in computation performance by using GPU.

CUDA enables computationally expensive programs to be computed at faster rates.

CUDA is typically used with the programming languages:
- C/C++
- FORTRAN
- ... Others do exist (Java wrappers).

## Why use GPU over CPU?
GPU provides greater amount of instruction throughput and memory bandwidth than CPU.
- Programs can utilise these benefits to run itself, or parts of itself, on the GPU: potentially running faster.

CPUs and GPUs are designed with different goals to achieve:
- CPUs designed to execute a sequence of instructions, referred to as a thread, as fast as possible.
- GPUs designed to execute thousands of threads in parallel.

In a GPU, more transistors are allocated to data processing rather than data caching and flow control like some transistors are in a CPU.