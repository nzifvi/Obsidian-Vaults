[[3,4,1) Storing Reference Types]] <- Back

---
## Object Header
All Objects have a header that contains vital information for the JVM
- 8 bytes for 32 bit systems.
- 12 bytes for 64 bit systems.

The object header stores...
1) class pointer (pointer to the class in Heap).
2) hash, age, lock.
	- All used to manage the object and it's state.

## Memory Use of Objects
Adding more data, beyond the header, results in additional memory being occupied by the Object.

Let pf denote primitive field
- Will be equal to the number of bytes required to store that primitive datatype.
Let of denote object field (a field which is a class type that references an object in memory).

```java
class Example{
	int a;
	byte b;
	double c;
	Object1 obj;
}
```

$$SizeObject(Example) = 12 +\sum_{n}pf_{n}+\sum_{m}[SizeObject(of_m) + 4]$$
- n = no. of primitive fields of the object.
- m = no. of object fields of the object.
Constant 12 for the object's header.

Constant 4 added to each object field as it is the memory occupied by the object's pointer.

To compute the memory occupied by an object with NO object fields... it is...

$$SizeObject(Example) = 12 +\sum_{n}pf_{n}$$
