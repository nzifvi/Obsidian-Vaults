[[2,1 - Free Store and Pointers]] <- Back
[[2,3 - Segmentation Faults]] <- Next

---
## What are Memory Leaks?
A memory leak occurs when heap memory, that was allocated to an object, is not de-allocated even after it's pointer goes out of scope.
- The allocated heap memory remains allocated, leading to waste.

## Problems caused by Memory Leakage

1) Reduced Performance.
	- As more and more RAM is occupied in a memory leak, performance decreases due to lack of available RAM.
2) Program Crashes due to potentially occupying all RAM.
	- If all RAM is eventually occupied by a memory leak, the program crashes.
3) Resource Depletion.


## How to avoid Memory Leaks
Deallocate memory once it is no longer needed.

- Destructors always deallocate.
- Use smart pointers.