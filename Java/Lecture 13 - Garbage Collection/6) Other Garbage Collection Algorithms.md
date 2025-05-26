[[5) Limitations of Garbage Collection]] <- Back

---
## Other Garbage Collection Algorithms
Developing, or optimising, garbage collection algorithms is an active field.

This is because...
1) Objects are often short lived. It is rare that an object will remain in scope for an entire program's duration unless it is declared in main.
	- Fields of an object referenced in main can change still. Objects update throughout a program's runtime.


2) Using as few resources as possible (time, memory): e.g. not using a free list.

3) Algorithms may trade ability to free space for efficiency.
	- However, objects that should be marked must still be marked to be preserved during garbage collection stage.

4) Algorithms may be able to run in the background WITHOUT having to interrupt, and pause, computation whilst garbage collection occurs.
	- Still using CPU cycles however.

5) Compacting memory, which has small gaps, may create free space
	- Plus, rearranging where memory is stored and updating the references so they still point to the correct value post rearrangement, would reduce the need to split up big objects in the event there is not enough consecutive memory in the Heap.