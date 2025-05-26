[[3,1) Memory Use]] <- Back
[[3,4,2) Object Memory Use]] <- Next

---
## Storing Reference Types
Primitive datatypes are stored by simply storing the actual value assigned to a primitive datatype variable in memory.

Reference types, like objects and arrays, DO NOT fit into a single word (4 or 8 bytes respectively) in memory.
- They can become very big.

Furthermore, when calling a method that takes object, or array, parameters. Passing by value requires a lot of copying to create a local copy of the passed object or array.
- A lot of data is copied to the memory for that method potentially.

Reference types are stored in their own bit of memory: the heap.
- Pointers are used to access them.
- Pointer = memory address. It has a fixed size of one word.
- Instead of passing an entire object, which may be many bytes, a pointer to the object is passed which is just 1 machine word.