[[1 - What are Copy Semantics]] <- Back

---
## What is a Shallow Copies?
A shallow copy results in the data members BEING shallow copied pointing to the same memory address.

```c++
AClass(const AClass& other):
data(other.data) // shallow copy
{

}
```

Shallow copies can result in double-delete bugs:
- If one of the copied objects go out of scope, and it's destructor deletes the memory at that address, the other object, still in scope, will attempt to access de-allocated memory.
- Best to deep copy contents of memory address if needing to copy them.