[[2 - How to Overload an Operator]] <- Next

---
## What is Operator Overloading?
In C++, operators such as +, -, << are all implemented as functions.
- In C++, a + b is essentially equal to operator+(a, b).

Overloading is the process of providing multiple variants of a function which all have the same name.
- This applies to operators too.

Operator overloading is when you provide a alternative declarations for an operator, such as +.
- The moment an operation is performed for 2 datatypes specified in an operator overload, the overloaded operator is called as opposed to the default.

## How calling operator overloads works.

If all of the operands of an operation are fundamental, built-in data types, the compiler will call the operators that are built in for them

If a SINGULAR operand is a user-defined datatype (a class, an enum, etc), the compiler will use the function overload resolution algorithm.
- Attempts to find an overload operator that is an unambiguous best match.
- If unable to find an unambiguous best match, compiler errors.
