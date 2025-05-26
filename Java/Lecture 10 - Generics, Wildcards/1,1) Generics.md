[[7,1) java.nio.Path and java.nio.File]] <- Back
[[2) Number Class]] <- Next

---

## What are Type parameters?
Type parameters are a way to specify a datatype of one, or multiple, field variables and or parameters during runtime.
- Allows for code to be more reusable. Instead of having multiple methods for different datatypes, just one is required when using generic parameters.

Type parameters can be used for...
1) Type variables.
2) Type parameters for methods...
3) Return values ?

## What is a Generic?

ANYTHING with a type parameter is referred to as a generic ...
- A method using generic parameters is a generic method.
- A class using generic parameters is a generic class.

## Defining Type Parameters
```java
public class Example <T>{
	private T first;
	private T second;
}
```

To define a type parameter, put an identifier within angled brackets <> in the method, or class, declaration.

- Convention is for type parameters to be capitalised.
- Consequently, class is now a generic class.

## Initialising a Generic Object
When initialising a generic object, the datatype the type parameter should be must be specified...

```java
Example<String> ex1 = new Example();
```

## Multiple Type Parameters
It is possible to specify multiple type parameters...

```java
public class TwoTuple <A, B>{
	private A firstElement;
	private B secondElement;
}
```

## Generic Methods
[[1,2) Generic Methods]]


## Generic Upper and Lower Bounds
[[1,3) Generic Upper Bounds]]
[[1,4) Generic Lower Bounds]]


