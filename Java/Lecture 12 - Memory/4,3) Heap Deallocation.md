[[4,1) Heap Organisation]] <- Back

---
## Heap Deallocation
When an object is created, make references to it throughout a program, and then forget about it.

- If we can refer to it then the memory, associated with that Object, might still be used. The JVM keeps it.

- If we no longer refer, or need, the object (no variable points to the Object in memory anymore), the JVM can free the memory allocated with it.
	- Freed memory can then be later used by JVM for future Heap allocations.

The process of the JVM identifying when allocated memory is no longer needed, and then deallocating it, is a process called garbage collection.

Some languages required manual garbage collection, such as in C/C++

Other languages, like Python and Java, do it automatically.