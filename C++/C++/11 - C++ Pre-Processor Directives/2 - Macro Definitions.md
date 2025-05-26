[[1 - What are Pre-Processor Directives]] <- Back
[[3 - Conditional Inclusions]] <- Next

---
## What are Macro Definitions?
A Macro definition allows for a replacement to be substituted in place of a macro throughout the entire source code.

A macro's replacement could be an expression, a statement, a block of code, or anything. However, it must adhere to the C++ syntax.

```c++
#define ARRAY_SIZE 100
int array[TABLE_SIZE];
```

After the pre-processor has finished and replaced TABLE_SIZE with it's replacement... the source code becomes...

```c++
int array[100];
```
## Function Macros
define can ALSO work with parameters, allowing function macros to be defined.

```c++
#define sum(a,b) a+b
```

## \#undef
undef allows for something, previously defined using a macro definition, to be undefined.

A macro lasts until it is defined with the \#undef pre-processor directive.

