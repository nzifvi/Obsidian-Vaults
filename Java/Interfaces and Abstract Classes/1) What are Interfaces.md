[[2) Abstract Classes]] <- Next

---
## What are Interfaces?

Interfaces are blueprints of classes, they contain methods that are related with each other.
- The methods in an interface are just method signatures, they have no body.

```java
interface Car{
	public void toggleEngine();
	public void refuel();
}
```

## Implementing Interfaces
An object of an interface cannot be initialised.
- An interface cannot have a constructor.

To access interface methods, the interface must be implemented by a class.
- The body of all methods, in the interface, is defined in the implementing class.

```java
class BMW implements Car{
	// ...
}
```

NOTE:
ANY abstract method that exists in an interface a class has implemented must be overridden and given a method body.

## What can be in Interfaces?

#### 1) Variables
An interface can have a variable, however they are always going to be...
- public access specifier.
- static.
- final (they will be an unchangeable value).

Because they are final, they must be initialised a value when the variable is declared.

#### 2) Methods
A method in an interface is public by default.
- Can be private in Java 8+

A method is also abstract by default in interfaces.
- An abstract method is a method without a body.

#### Since Java 8...

An interface's methods can be default, not abstract.
- A body with a method.
- Can be overridden by classes implementing the interface.

An interface's methods can be static.
- Static methods have a body.
- They cannot be overridden as they belong to the interface.

ANYTHING that is static can be referred to anywhere in a program.
