[[5 - Expressions]] <- Back

---
## What are lvalues and rvalues?
Every expression in C++ has a type and belongs to a value category.

![[Pasted image 20250715155219.png]]

Value categories are fundamental building blocks which are used to build rules for compilers to follow when...
1) Creating.
2) Copying.
3) Moving
...temporary objects during the evaluation of an expression.

The value categories themselves are used to determine how an expression can behave and what can be done to terms of an expression.
- Object identity.
- Lifetime of an object.
- If an object is modifiable or not.

## How Compiler Uses Value Categories
For any given expression...
```
lhs = rhs
```
(lhs or rhs can be nothing as well).

1) Compiler first evaluates the value category of LHS.
2) Compiler then evaluates the value category of RHS.
3) Checks if the assignment of RHS to LHS is valid.
	- LHS must be an lvalue, or a reference to an xvalue, in order to assign something to it.
	- RHS MUST be convertible to be the same type that LHS is (int = int) for example.

If 3 is true, assignment is performed...
- RHS value is copied/moved to the memory address of the variable object or reference to an object in the LHS.

## locator value (lvalue) expressions
An expression which refers to an object with an identity that ALSO has a persistent memory address that can be taken.

Examples:
- int x;
- x (if x was declared beforehand);
- int* x (pointer to x in memory);
- int& f(); (function returning a reference to an int type).
- int& x; (a reference);


## expiring value (xvalues) expressions
Expiring values have an identity and still refer to an object. However, that object in memory will soon be reused or destroyed.
- xvalues allow for move semantics: moving memory instead of having to copy (useful for encapsulation).
- xvalues are usually created when an lvalue is casted to an rvalue reference (std::move(x)), or a function returning an rvalue reference.

## prvalues
A prvalue has NO identity nor addressable storage. 
- prvalues are usually a pure value (result of 3+1) OR a temporary object.
- Usually result of a literal, arithmetic expression, or a function returns by value instead of by reference.

prvalues usually used to initialise variable objects or compute values.


