[[2) Java Memory Model]] <- Back


## Memory Use
Memory can be treated as an array of values. Each value is addressable by an index and each element holds a byte of data.
- Memory is addressed to get blocks of 32 or 64 bit words.
	- 32 if on a 32 bit system.
	- 64 if on a 64 bit system.

![[Pasted image 20250412050640.png]]
This is done so that memory is aligned and "complete"

In Java, Objects occupy multiples of 8 bytes and are stored in the Heap.

In Java, primitive data types (int, floats, etc) typically require 1 or 2 words to store (1 or 2 bytes as each array element = 8 bytes).1!