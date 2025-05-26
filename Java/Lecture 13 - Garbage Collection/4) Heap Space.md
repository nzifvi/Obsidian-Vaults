[[3,1) Garbage Collection in Java]] <- Back
[[5) Limitations of Garbage Collection]] <- Next

---
## Heap Space
The Heap starts with a default size.
- Default size can be manually set, using parameters if required.

When allocating new memory in the heap, JVM will attempt to use free spaces, in the free list, first.
- Matching allocation requests to holes reduces gaps in memory use.
- Keeping objects together improves cache performance.

When the heap becomes full, garbage collection is automatically called to try and create more free spaces for the free list.
- If no free space can be generated, the Heap is expanded.
- However, the Heap size can only be expanded up to a finite limit.
- If no space can be freed, and the Heap cannot be expanded, a crash occurs.