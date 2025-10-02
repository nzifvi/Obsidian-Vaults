 [[4 - References]] <- Back
[[6,1 - lvalues and rvalues]] <- Next

---
## What is an Expression?
An expression is a part of a statement which produces a value, or computes something, when it is evaluated

![[Pasted image 20250715150812.png]]
At runtime, expressions do work: computing values, modifying memory, etc.

Examples to expressions:
- Returns of function calls.
- Memory accessing.
- Mathematical expressions.

Expressions can also have side effects.
- Expressions can also change the program state whilst returning a value.

All expressions evaluate to a VALUE (a result formed by an expression).
- A Value of an expression may potentially be an object.
- A Value might not be an object at all (non-object value).
	- Results of pure computation not assigned to anything.
- A Value might even be void, which means there is NO result.


