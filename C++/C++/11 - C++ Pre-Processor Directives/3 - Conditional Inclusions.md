[[2 - Macro Definitions]] <- Back

---
## What are Conditional Inclusions?
Conditional inclusions are a type of directive that allow the inclusion, or discarding, of part of the source code if a given condition is not met.

Note: any conditional inclusion block must be terminated using \#endif pre-processor directive.
### 1) \#ifdef, \#ifndef
\#ifdef allows a section of source code to ONLY be compiled if the macro that is specified as the parameter has been defined, REGARDLESS of the macro's value.

```c++
#define ARRAY_SIZE 100
#ifdef ARRAY_SIZE
int table[TABLE_SIZE];
#endif
```

\#ifndef is the opposite. The source code between an \#ifndef and the \#endif pre-processor directive is only compiled if the macro given as the parameter has NOT been defined.
```c++
#ifndef ARRAY_SIZE
#define ARRAY_SIZE 100
#endif

int table[TABLE_SIZE];
```