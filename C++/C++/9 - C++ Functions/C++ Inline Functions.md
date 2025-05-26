
---
## What are Inline Functions
Inline functions are a way to optimise a program's performance by reducing the overhead created when a function is called.

When a function is specified as inline, the code block of the inline function is substituted in place of the function call when called during compilation.
- This prevents the function actually being called, preventing a function call from occurring.


A function CANNOT be an inline function if...
- Contains a loop.
- Contains static variables.
- Is a recursive function.
- Contains a switch or go to statement.

## Inline Function Syntax
```c++
inline returnType functionName(parameters); 
```


## Virtual vs Inline Functions
A virtual function CANNOT be inlined. This is because they are handled during different times.

- Virtual functions wait until runtime to figure out which derived class function to call based on the object that has called it. It is unknown what function could be called.
- Consequently, no inlining can occur as it is unknown what function could be occurred.