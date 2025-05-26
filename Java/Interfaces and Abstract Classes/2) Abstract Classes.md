[[1) What are Interfaces]] <- Back

---
## What are Abstract Classes?
Abstract classes are a type of blueprint classes that provide more functionality than interfaces.

Abstract classes differ from interfaces.
- Abstract methods can exist.
- Concrete methods (methods with bodies) can exist without being default or static.
	- Therefore they belong to objects of classes that extend the abstract class.
- Abstract classes can have constructors.
	- They can be overridden.
- Can have variables that are uninitialised in the abstract class.

Like interfaces, abstract classes cannot be directly instantiated.

## When to use Abstract Classes

Interfaces are used when a set of classes share a group of methods but want to use them differently.

Abstract classes are used when...
- wanting to share code among classes which extend the abstract class.

- The classes extending the abstract class should be expected to have many common methods and or fields.

- When fields are desired to be non-static and non-final.
	- Recall: fields of an interface are always static and final. They cannot be anything else.


## Using Abstract Classes

```java
abstract class Layer{
	//stuff in the abstract class
}

class ConvoultionalLayer extends Layer{
	/*
	The class implementing the abstract class
	can...
	
	1) Override methods to get different
	   behaviour.
	   
	2) Use concrete methods.
	   
	3) Assign values non-final, non-static 
	   fields.
	*/
}
```

Any methods declared as abstract in the abstract class MUST be overridden and given a body in the implementing class.

Abstract methods CANNOT be private as classes which implement the abstract class must be able to access them to override them.