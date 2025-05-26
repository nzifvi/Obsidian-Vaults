[[3,1) Memory Use]] <- Back

---
## Arrays
Arrays, in Java, are a sort of object for memory management

By default, an array occupies 16 bytes of memory BEFORE any data is added.
- These 16 initial bytes referred to as "overhead" or the Array Object Header.
- Contains info about the array.
	- 8 bytes for mark word (hashcode of array, GC info).
	- 4 bytes for the class pointer (compressed version).
	- 4 bytes for the length of the array.

```java
int[] array = new int[0];
```
- Array of 0 elements occupies 16 bytes by default.

Each cell of an array holds a value

Even though an int occupies 4 bytes in memory, each cell adds 8 bytes of memory occupied for an array of ints.
- Because modern 64 bit JVMs use 8-byte alignment for efficiency.
- Memory allocator rounds up the allocated memory, per cell, to 8 bytes.

So... to calculate how much memory below array occupies...

```java
int[] array = new int[5];
```

$$\sum_{i=0}^{n - 1}[x]$$
n = number of elements
- If i = 0, x = 16
- Else, x = 8

So... using above formula...
$$16+8+8+8 = 40$$
Therefore the array occupies 40 bytes of memory currently.