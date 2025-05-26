[[1) Dereferencing]] <- Back
[[3,1) Garbage Collection in Java]] <- Next

---
## Garbage Collection
When an object is no longer referenced by any other object. It can never be accessed again.
- It is lost to the program forever.
- It is garbage.

The memory garbage occupies can be freed and then reallocated for future allocations to the Heap.

A garbage object can still have references to other objects. However, it is disconnected from the graph of currently in scope, and referenced, objects.
- If ONLY the garbage object references the objects it does, those objects too are also garbage.
- The garbage collection process might discover entire disconnected sub-graphs of garbage objects.

```java
personalCar.setCarTank(null); //causes a dereference
```

This causes for part of the object graph, which an object is the root node of, to be separated. The separated sub-graph is all garbage.

![[Pasted image 20250412125857.png]]
