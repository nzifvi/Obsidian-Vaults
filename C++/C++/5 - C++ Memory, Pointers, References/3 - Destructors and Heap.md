[[2,1 - Free Store and Pointers]] <- Back
[[4 - Pointers to Class objects]] <- Next

---
## Destructors and Heap
When a class uses heap allocations, they must eventually be deallocated at some point to prevent memory leaks.
- The class' destructor can do this. When the class goes out of scope, the destructor is called.
- Destructor de-allocates all heap memory, using delete and or delete\[\].

