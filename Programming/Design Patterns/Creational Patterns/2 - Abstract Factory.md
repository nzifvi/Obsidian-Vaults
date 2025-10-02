[[1 - Builder]] <- Next

---
## What is an Abstract Factory Pattern?
Suppose you have 3 classes: A, B,C and each has a type
- These 3 classes, A,B,C also have variants of themselves:
- The types are 1, 2, 3.

$$
A_1, A_2, A_3
$$
$$
B_1, B_2, B_3
$$
$$
C_1, C_2, C_3
$$

This would require 9 classes.

An abstract factory is essentially a builder for multiple groups of related objects where...
A is a group.
B is a group.
C is a group.

and...

1 is a type.
2 is a type.
3 is a type.

### Examples of these groups...

$$
Car_{engine1}, Car_{engine2}, Car_{engine3}
$$
$$
Truck_{engine1}, Truck_{engine2}, Truck_{engine3}
$$

And A, B, and C are unrelated to each other.

## Creating an Abstract Factory
### Declaring and Defining Products
Before creating the abstract factory, abstract products should be made.
- Abstract products are the groups to which each set of objects belong.
- Implemented using interfaces

```c++
class A{
private:
public:
	A(){};
	virtual ~A() = default;
	// Any other function members which all A classes share
}
```

Then each class of that group implements the interface...
- These are called the concrete products, because they are implementations of the abstract product (the interface)

```c++
class A1 : public A{
	// ...
};

class A2 : public A{
	// ... 
}

class A3 : public A{
	// ...
}
```

Suppose this is done for all groups A, B, C.

### Declaring and Defining The Factories
First, an abstract factory must be made.
- Implemented as an interface.
- The abstract factory will have a make function member for each group: A, B, C...


```c++
class AbstractFactory{
private:
public:
	AbstractFactory(){};
	virtual ~AbstractFactory() = default;
	
	virtual A* makeA();
	virtual B* makeB();
	virtual C* makeC();
}
```

Then, for each variant, a concrete factory is made.
- Groups 1, 2, and 3.


```c++
class Type1Factory{
private:
public:
	Type1Factory(){};
	~AbstractFacotry() override{};
	
	A* makeA() override{};
	B* makeB() override{};
	C* makeC() override{};
}
```
- Do for all types 1, 2, 3...

EACH concrete factory will be able to produce a types from a specific group.