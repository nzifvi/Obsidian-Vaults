[[8,1) ArrayList]] <- Back

---
## Vector
Vector is similar to an ArrayList, however, there are times where a Vector should be used instead of an ArrayList.

With a Vector, you can control the initial capacity and by how much the Vector grows by when a resize is required.
- The initial capacity, and the amount of increment the current capacity, passed as parameters to Constructor when initialising a vector


## Vector Constructors

1) Constructor with no parameters
	- Has a size of 10 by default.
	- Standard capacity increment is zero (does not resize)
```java
Vector<Integer> vec = new Vector()<>;
```

2) Constructor with initialCapacity parameter
	- Has a fixed size determined by parameter.
	- Standard capacity increment is zero (does not resize).#
```java
Vector<Integer> vec = new Vector(5)<>;
```

3) Constructor with initialCapacity and capacityIncrement parameters.
	- Has a fixed initial size, determined by initialCapacity parameter.
	- When required to resize (when size == capacity), capacity will grow by current capacity + capacityIncrement.
```java
Vector<Integer> vec = new Vector(5, 10);
```


## When to use a Vector and not an ArrayList
Vectors are thread safe, meaning that it can be accessed by different execution threads.
- When multi-threading, use Vectors and not ArrayLists. Vectors are designed to be safe for multiple threads to access them whilst ArrayLists are not.
- Only one thread gets to use a Vector at any given time, all others have to wait.
- Using an ArrayList across multiple execution threads risks corruption.