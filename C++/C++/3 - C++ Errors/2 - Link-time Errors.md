[[1 - Compile-time Errors]] <- Back
[[3 - Run-time errors]] <- Next

---
## What are Link-time Errors?
A program may consist of several parts that are compiled separately. These parts are referred to as translation units.

Each function in a program MUST be declared with exactly the same type in EVERY translation unit in which it is called.
- Header files are used to ensure that.

Every function must also be defined exactly once in the program.
- If a function declaration lacks a function definition, this above rule is violated.

If either of the above rules are violated, a link-time error occurs.