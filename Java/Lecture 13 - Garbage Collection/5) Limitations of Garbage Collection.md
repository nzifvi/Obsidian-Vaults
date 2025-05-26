[[4) Heap Space]] <- Back
[[6) Other Garbage Collection Algorithms]] <- Next

---
## Limitations of Garbage Collection
Although garbage collection is a simple concept AND very helpful. It has it's limitations. The limitations are...

1) No useful computation can occur whilst garbage collector is occurring.
	- This is because nothing can be allocated to Heap as it is being marked and swept.

2) The graph of objects to traverse in the mark stage of mark-sweep algorithm may be very complex and take a lot of time.

3) The Heap is big and linearly searching it will take time.

4) Memory is occupied by the Heap's free list. More memory is required to try and optimise memory usage.

5) If the memory becomes fragmented, it might not be possible to allocate a big object into Heap.
	- If this occurs, the big object must be split up.
	  
	  Suppose this is the current state of the Heap![[Pasted image 20250412132348.png]]
		All white squares are in the Heap's free list.
		
		A request to allocate memory for an object in the Heap, described in the below image, is received
		![[Pasted image 20250412132517.png]]
		There exists no space where a block of consecutive memory can be allocated for the object. JVM splits up the object into multiple parts and stores each segment where it can in the Heap.
		
		![[Pasted image 20250412132618.png]]
		
	
