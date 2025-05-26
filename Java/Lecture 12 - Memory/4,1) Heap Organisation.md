[[3,1) Memory Use]] <- Back

---
## Heap Organisation

![[Pasted image 20250412080458.png]]

Objects in the Heap can be different in size. It all depends on how much memory each object occupies.

Furthermore, objects referred to in the fields of an object can be stored in different parts of the Heap memory area.
- The reference, aka pointer, provides the address to locate an object field in the Heap.
- An object, which is a field of another object, is not part of that object. It exists independently in memory.

When keyword new is called, or some process calls new automatically, a chunk of the cheap is allocated. This [[4,2) Heap Allocation]] consists of...
1) One word saying how long it is.
2) One word pointing to the class.
3) One word for EACH field.

Once an object, or Array, in the Heap is no longer required, [[4,3) Heap Deallocation]] occurs.