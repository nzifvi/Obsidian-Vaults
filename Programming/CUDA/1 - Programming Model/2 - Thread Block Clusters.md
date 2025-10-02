[[1 - Kernels, Threads, Thread Blocks, and Grids]] <- Back
[[3 - Heterogeneous Programming]] <- Next

---
## What are Thread Block Clusters?
CUDA programming model provides an additional level of hierarchy which is entirely optional: thread block clusters.

A thread block cluster is a group of thread blocks

Thread blocks in a thread block cluster will always be co-scheduled together on a GPU Processing Cluster (GPC) in the GPU.

Like thread blocks, thread cluster blocks can be 1D, 2D or 3D.