[[3 - Destructors and Heap]] <- Back

---
## How do Pointers to Class objects work?
Pointers, in general, can be used to point to anywhere in memory.
- Pointers to a class object can even exist.

When creating a class object on the heap, the new operator...
1) First allocates the required memory for the class object.
	- Can determine the amount that will be allocated using the sizeof operator.
2) Invokes the class object's constructor to initialise that class object.
	- Class object's constructor further allocates memory for the class object's data and function members.

When a class object is deallocated, using the heap operator...
1) The class object's destructor is invoked first.
2) Then the delete operator deallocates the heap memory that was allocated for that class object.