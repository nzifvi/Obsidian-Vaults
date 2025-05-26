[[1,1 - Memory, Addresses, and Pointers]] <- Back

---
## Free Store and Pointers
When a C++ program compiles, the compiler sets aside...
- Memory for code, called code storage or text storage).
- Memory for globally defined variables, called static storage.
- Memory for functions, and their arguments, called stack or automatic storage.

The rest of the computer's memory is then available for other uses. This area of memory is called free store.
- C++ accesses this free store, aka heap, through the new operator.

```c++
double* p = new double[4]; //allocates 4 doubles to heap.
```

new is used to allocate an object, or multiple objects, to the heap and return a pointer to the object(s).
- If allocating a single object to heap, new returns a pointer to the object it allocates.
- If allocating multiple objects to heap, such as an array, new returns a pointer to the first of those objects in the sequence.

### Heap (Free Store) Allocation
Memory allocation on the heap can be requested using the new operator.
- New operator returns pointer to the allocated memory.
- Pointer value is the address of the first byte of memory.
- A pointer points to an object of a specified data type.
- A pointer does NOT know how many elements it points to.

```c++
double* ptrDouble = new double; // allocates 1 double to heap

double* ptrDouble = new double[n]; // allocates n doubles (an array of doubles) to heap
```


### Heap (Free Store) Deallocation
Since a computer's memory is limited, memory should be freed on the heap once it is done being used.
- Deallocating heap memory once done allows for it to be re-used.
- For large/long running programs, freeing memory is crucial.

The delete operator is used to deallocate memory pointed to by a memory address.
- delete frees memory for an individual object, prev. allocated by new operator.
- delete\[\] frees memory for an array of objects, prev. allocated by new operator.

```c++
int* ptrInt = new int;
int* ptrIntArray = new int[4];

delete ptrInt; //de-allocated heap memory, freeing it.

delete[] ptrIntArray; //de-allocated heap memory, freeing it.
```

NOTE: attempting to delete already deleted memory is dangerous.
- It returns a run-time error.

Reasons why attempting to delete already deleted memory causes an error:
1) You do not own the object pointed to anymore. Upon delete being performed, the heap manager now owns that memory. It might have even changed the internal data structure, which is why delete may not be performed twice.

2) Heap manager might have already re-used that memory previously deleted to now be allocated for something else.

#### [[2,2 - Memory Leaks]] 