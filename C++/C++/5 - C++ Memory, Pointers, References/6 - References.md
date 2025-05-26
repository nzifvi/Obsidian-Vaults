[[5,1 - void pointer and casts]] <- Back
[[7 - Pointers and References as Parameters]] <- Next

---
## What are References?
References are an alternative to always using pointers to access objects in memory.

References are an automatically dereferenced, unchangeable pointer for an object in memory.
- References are immutable: they cannot be made to refer to another object after initialisation.
- References are a deep copy. They refer to the object in memory itself.
	- Pointers are not deep copies. They point to the object via a memory address. You have to dereference a pointer to access the object.

BOTH pointers and references use a memory address of an object.
## Declaring and Initialising References
Declaring a reference variable is done using the address of, &, operator in place of the pointer operator *

```c++
int x = 42;
int& refX = x;

```

To assign a value to a reference variable, let it equal a variable which has the same data type.

## When to use References vs Pointers
If different objects have to be pointed to over time, use pointers.
- Because pointers can be assigned again and again after initialisation.

If only having to point to one object and that will never change, use references.
- Because references cannot be assigned another memory address after initialisation.


