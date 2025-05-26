[[2,2 - Memory Leaks]] <- Back

---
## What are Segmentation Faults?
A segmentation fault is an error that happens when a program attempts to access a memory location that it does not have permission to access.

A segmentation fault may be caused by...
1) Accessing memory that the program does not own.
	- Occurs when accessing out of bounds array indices.
2) Attempting to dereference, an uninitialised, a nullptr, or NULL pointer.
3) Modifiy read-only memory.
4) Stack Overflows
5) Buffer Overflows

