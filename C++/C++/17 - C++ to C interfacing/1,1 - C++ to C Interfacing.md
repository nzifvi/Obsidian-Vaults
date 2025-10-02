[[1,2 - Calling C in C++ Program]]]

---
## Problem with Interfacing

C code can be used in a C++ program and C++ code can be used in a C program if done correctly.

It cannot be done without certain things being done as C++ uses name mangling to handle function overloading.
- By overloading a function, you create multiple definitions all with the same name.
- This creates multiple functions, all with the same name, (mangling the names).
- C++ compiler stores additional information about functions in memory to determine which one is the one to be called.
- C compiler does not support this hence it must be accounted for.

## Why Interface?
C libraries, especially ones for low level programming / hardware control, can be utilised in a C++ program.