[[3,1) Garbage Collection in Java]] <- Back

---
## Garbage Collection Algorithm
There are multiple ways to implement garbage collection. One is the mark-sweep algorithm.

Mark-sweep algorithm has 2 phases:
#### 1) Mark:
Look through the heap and mark the objects that are needed (objects currently referenced by non-garbage objects all the way to their root reference (first object which begins the graph of references AND is in scope)).

#### 2) Sweep:
Look through the heap again and free the unmarked objects (objects which are not referenced OR are referenced by a garbage object).
- Consequently deallocates memory in the Heap.

### Marking
Objects which are...
1) Referenced to by a variable in the program currently in scope.
2) Referenced to by a field variable, of an object, that is in scope.
3) Referenced to by a field in some kind of object referenced in another object
Must all be marked to be kept

This requires a recursive algorithm to recursively search through object's reference graphs.

#### Recursive Algorithm for Mark-Sweep
Start with main method's variables and recursively search each, traversing the graph by reference.

For each object:
- If it is marked already, do nothing: prevents loops from occurring in sweep stage.

- If it is not marked, mark it and make a recursive call over each of that object's fields.

At some point, the recursive algorithm will eventually reach an object with ONLY primitive fields. No more references to follow.
- Terminate the recursive algorithm.
- This is the base case.

### Sweeping
JVM maintains a free list.
- Free list = a map of the free chunks of memory in the Heap.

Sweeping can pass linearly through the heap, starting at the very first chunk of the Heap map.

Sweeping stage then performs a check for each chunk it is currently at.
- If the current chunk is NOT marked, add the space for this object to the free list.
- RECALL each object describes how much memory it occupies.

Then, move forward to address(currentAddress + thisObject.size) to find next object OR free chunk if the address is free.

Above process is repeated until last chunk visited.