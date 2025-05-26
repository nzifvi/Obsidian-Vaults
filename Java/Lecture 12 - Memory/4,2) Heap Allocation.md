[[4,1) Heap Organisation]] <- Back

---
## Heap Allocation
Heap Allocation is the process where the JVM allocates memory, in the Heap, for an object of array after the new keyword was executed.

To allocate memory, the JVM has to...
1) Calculate the amount of memory required by the object, or array. 
	- Determined by it's type or class.
2) Allocate that memory from spare space in the heap and adjust the pointer to the end of the heap.
3) Store the size, class, and field data of the object.


Dynamic data structures (dynamic arrays, linked lists, etc) which can grow over time usually set a default size for their container in the heap.
- As data structure grows during runtime, new allocations are required to grow the container.