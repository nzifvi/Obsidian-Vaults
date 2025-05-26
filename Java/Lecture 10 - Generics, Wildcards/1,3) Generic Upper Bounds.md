[[1,2) Generic Methods]] <- Back

---
## What is a Generic Upper Bound?
Without an upper bound, a type parameter can later taken on the form of any class...
- Sometimes, this is not wanted.
- Instead of taking on any possible class, suppose you want a generic method, or class, to only take on a few possible classes.

An upper bound type parameter means that only sub classes, or the class used as an upper bound itself, can be specified as the type parameter.
- No super classes of the upper bound type parameter can be specified as the type parameter.

To do this...

```java
class A1<T extends RequiredClass>{
    //class definition...
}
```

extends means "extends or implements or equals"

If the RequiredClass, that will be the upper bound for the generic class, is also a generic class, you must also specify the type parameter's data types...

```java
class A1<T extends RequiredClass<T>>{
	//class definition...
}
```