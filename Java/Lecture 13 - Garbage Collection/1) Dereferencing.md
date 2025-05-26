[[7,1) Copies]] <- Back
[[2) Garbage Collection]] <- Next

---
## Dereferencing
When objects reference other objects, through variables known as references, then there is a graph of objects formed by the references.

```java
class Car{
	Engine carEngine;
	Tank carTank;
	//...
}

class Engine{
	Fuel engineFuel;
	//...
}

class Tank{
	Outlet tankOutlet;
	//...
}
```

Suppose, in main...
```java
public static void main(String[] args){
	Car personalCar;
}
```

An object of Car is initialised. Setting off a chain of initialisations.
- Multiple objects initialised and memory, in the Heap, is allocated for them.
- A graph is formed through the references found in the objects.

Graph of objects, related by references...
![[Pasted image 20250412125056.png]]

When a variable is allocated a new value OR if a variable goes out of scope, the references vanish.
- As long as there is one reference, part of the object, still in scope: the object will continue to exist.
- The moment all references go out of scope is when the memory allocated to that object is freed (GARBAGE COLLECTION).
- The above is why local variables can be reused.
- The above is also why local variables can be used for objects which are then referenced, by assignment to the local variable, through a graph of references to some other object.

```java
//suppose x is an object of the Outlet class
personalCar.getTank().getOutlet() = x;
```

![[Pasted image 20250412125434.png]]
