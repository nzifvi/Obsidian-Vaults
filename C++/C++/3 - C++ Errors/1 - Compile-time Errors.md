[[2 - Link-time Errors]] <- Next

---
## What are Compile-time Errors?
Compile-time errors are typically...
1) Syntax errors.
2) Type errors.

The compiler, before generating the resulting object code file, analyses the program and ensures it 100% conforms to the language specification.
- Most compile-time errors due to mistyping or incomplete edits of source code.
- Others result from flaws of understanding of how parts of a program interact.

Compiler = your best friend. It catches errors that would potentially take hours of debugging and research.

### Syntax Errors
Syntax errors are caused by something in the source code not adhering to the rules of C++ grammar.
- If a syntax error is found by compiler, the compiler aborts compilation and flags a syntax error.

Example of some things that cause syntax errors:
```c++
int s1 = area(7; // syntax error: missing )
int s2 = area(7) // syntax error: missing ;
Int s3 = area(7) // syntax erro: Int is not a type
```

Syntax errors are not always easy to understand the meaning of.
- The report of a syntax error can be confusing, full of vague language.
- Because compiler may have to read a bit further than the point of the syntax error to confirm whether it is indeed a syntax error.

NOTE: Compiler has no idea what the programmer attempts to do. It cannot report syntax errors in terms of intent.
```
error: mispelled datatype int, do not capitalise N.
```

It only can report in terms of what has happened and flagged the syntax error. It cannot make recommendations to fix the syntax error as it does not know what was trying to be done.

### Type Errors
The compiler will always check for syntax errors. If none are found, it begins checking for type errors.

A type error occurs when...
- A variable is assigned a different data type than the data type it was declared to be.
- A function is passed an argument with a different data type than the parameter was specified to be in the function's parameter list.

Compilers report type errors.