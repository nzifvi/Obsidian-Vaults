[[2 - Thread Block Clusters]] <- Next

---
## What are Kernels?
Kernels are a special type of C++ function that, when called, are executed $n_{times}$ times in parallel by $n_{threads}$ different CUDA threads.

### Declaring and Defining a Kernel
A kernel is declared and defined using the... ```__global__``` declaration

```c++
__global__ void vecAdd(float* A, float* B, float* C);

int main(){

}

__global__ void vecAdd(float* A, float* B, float* C){
	int i = threadIdx.x;
	C[i] = A[i] + B[i];
}
```

To call a kernel, do...
```c++
vecAdd<<nBlocks, threadsPerBlock>>(...);
```

Each thread will execute the kernel once and only once, explained in What are Blocks.

## What are Threads?

## Thread Hierarchy
threadIDx is a 3-component vector, providing 3 indices in each dimension (i, j, k) to uniquely identify an index in 1d, 2d, or 3d space.
- Enables computation in 1 to 3 dimensions.

```c++
const int numOfBlocks = 1;
dim3 threadsPerBlock(iDimensionAmount, jDimensionAmount); 
```

Groups of threads will share the same dimensions, forming a thread block.
- Thread block will have equivalent dimensions to the threads forming the thread block.
- 1d threads form 1d block, 2d threads form 2d block, etc.

## What are Thread Blocks?
Blocks are a group of threads that run together on a Streaming Multiprocessor (SM).

The threads $\in$ a block can...
1) Communicate with each other, using shared memory in that block.
2) Can be synchronised with \_\_syncthreads() (discussed later).

When calling a kernel, a number of blocks, and the amount of threads to be allocated per block, can be given as arguments.

The number of times a kernel will execute depends on the number of blocks and the number of threads per block.
$$
total_{executions} = n_{blocks} \cdot \frac{n_{threads}}{n_{block}}
$$
- Therefore, number of threads = total executions.

There is a hard limit on the number of threads, per block.
- Because...
	1) All threads $\in$ a block are expected to reside in same SM.
	2) Must share limited memory resources in the core of the SM.
- On current GPUs, hard limit of number of threads per block = 1024 threads.

Thread blocks are required to execute independently.
- Must be possible to execute the thread blocks in any possible order, in parallel, or in series.
- Independence requirement enables thread blocks to be scheduled in any order, across any number of cores.
	- Allows code that scales with the number of cores to be written.

### Thread indexing
The index of a thread in a block and it's ID are related as such:
- for 1d blocks, the rectangular components of a thread are equal:
	```threadId.x = threadId.y = threadId.z```
- for 2d block of dimensions (Ax, By), the thread ID of a thread of index (x, y) is equal to (x + y*Ax).
- For 3d block of dimensions (Ax, By, Cz), a thread's ID, of index (x,z,y) is equal to (x + y*Dx + z*Dx*Dy).

### Thread Syncing
Threads, within a block, can work together by sharing data via shared memory AND by synchronising their execution to coordinate accessing shared memory.
- Specific points in a kernel can be specified to make threads synchronise.
- Using \_\_syncthreads() function, which ensures all threads within a block must wait before any are allowed to proceed. 
## Grids
Thread blocks are organised into 1D, 2D, and 3D grids of Thread blocks.
![[Pasted image 20250724131507.png]]

Number of Thread blocks in a grid typically depend on the size of the data being processed.

Each Thread block $\in$ a grid can be addressed using a uniquely assigned index, accessible within the kernel via the ```blockIdx``` variable.

The dimension of the Thread block is accessible, within a kernel, via ```blockDim``` variable.

