[[1,1 - C++ to C Interfacing]] <- Back

---
## Calling C in C++ Program
To achieve this, the reserved word extern, with char C, is used.
- This specifies that the given symbol, C, has an external linkage to something else. 
- It defines a global variable, C in this case.

The C header file must be structured as:
```c
#ifndef LIBNAME_H
#define LIBNAME_H

#ifdef __cplusplus
extern "C" {
#endif

// code goes here...

#ifdef __cplusplus
}
#endif

#endif
```

extern "C" in header prevents name mangling, only one variant of this function will be able to exist.

ifdef __cplusplus ensures the header is safe to use in both a C and C++ projecct.

NOTE: The header file is what is wrapped via the extern reserve word.
- If any third party library does not wrap it already, it can be done by wrapping the include statement in a extern block.

```c++
extern "C" {
	#include "CLibrary.h"
}
```

- Can also do this if you are unsure a library is wrapped for use in C++ just to make sure it is.