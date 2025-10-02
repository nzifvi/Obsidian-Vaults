[[3,1 - Allocating Memory to Devices]] <- Back

---
## Copying Memory between Host and Device
Before performing any computation by calling a kernel, the device memory must be loaded with data to operate on.  

After kernel operates on data that was copied into device memory, the result is stored in device memory.
- Has to be copied back to host memory for the host to utilise it.

All of this is done using the ```cudaMemcpy()``` function, which takes multiple arguments on call.

```
cudaError_t cudaMemcpy(void* dst, const void* src, size_t count, enum cudaMemcpyKind kind)
```
dst is a void pointer, later cast in cudaMemcpy() function, which is the address to copy memory to.

src is a const void pointer, later cast, which is the address to copy memory from.

count is the size, in bytes, of memory which will be copied from src address to dst address.

kind specifies the type of copy.

kind can equal...
1) cudaMemcpyHostToHost
2) cudaMemcpyHostToDevice
	- Used to load data to a region of device memory, before Kernel call.
3) cudaMemcpyDeviceToHost
	- Used to load data, in device memory, to host memory (usually done to get results of Kernel into host memory).
4) cudaMemcpyDeviceToDevice