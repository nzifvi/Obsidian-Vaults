[[2 - Variables]] <- Back
[[3,2 - Type Safety]] <- Additional
[[4 - References]] <- Next

---
## Variable Objects
In C++, an object is a region of memory with a type and optional name.
- This region stores data relating to that object.

An object has an **identity** which is used to refer to it throughout the program.
- Variable names.
- Using it's memory address.
- Binding it to a reference.

By doing 1 of the 3 above options, the identity of an object is made **persistent**.
- persistent objects have a lifetime that are controlled by a programmer, unlike temporary values.
- Objects with a persistent lifetime referred to as variable objects.

Anything object which has a persistent identity can...
- Have it's address taken using the address-of operator (&).
- Be modified later in the program.
- Bound to T&, where T is the object's type, or const T&.

## Temporary Objects
A temporary object is an unnamed, short-lived object created from the evaluation of an expression.
- Still has an identity
- Temporary objects are very short-lived, they are wiped from memory automatically once the full expression is evaluated.


Because they are lost once an expression is fully evaluated, they cannot be modified.
- Lifetime (how long an object lives for in memory) can be extended by binding it to a reference [[4 - References]]
- Without binding, because it is immediately cleared from memory post evaluation, a temporary object cannot be modified.

Their address CAN be taken but only if their lifetime is extended (temporary object made into a variable object).
- Done by binding it to a reference.
- Once extended, a temporary object becomes addressable via it's reference


Temporary objects, as they are the result of an expression, are usually...
1) Return values of functions.
2) Literal expressions.
3) Results of operators/constructors.



