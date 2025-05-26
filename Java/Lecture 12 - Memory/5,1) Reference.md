[[4,1) Heap Organisation]] <- Back
[[6,1) Aliases]] <- Next

---
## References
Object variables are a REFERENCE to that object's class type, or a subclass of the class type.

References occupy 1 memory address. In Java that is about 32 bits post compression.
- Java compresses 64 bit reference so it just takes 32 bits.

Objects themselves can contain fields which are...
1) Arrays.
2) Objects.
3) Arrays of references to objects.


## Reference Values
Expressions of reference type, including objects and arrays, evaluate to pointers.

After running the assignment...
```java
int[] x = {1, 2, 3};
```

The value of x is a pointer to the array.

Furthermore, after the running the below assignment...
```java
Integer y = new Integer(4);
```

The value of y is a pointer to an object, with the type Integer, and the pointer points to an address in Heap.

