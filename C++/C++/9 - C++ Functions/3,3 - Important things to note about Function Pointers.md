[[3,2 - Function Pointers as Parameters]] <- Back
[[3,4 - standard lib function]] <- Next

---
## Important things to note about Function Pointers

### 1) Default arguments of a function do not work with Function Pointers
When calling the function at the memory address assigned to a function pointer, it's default arguments do not work.

- Default arguments of a function are resolved at compilation time. The compiler re-writes the function call to have the default argument, unless another value is put in place.

- When a function is called via a function pointer, it is resolved at runtime. Therefore, the compiler CANNOT re-write the function call. 

- This is why default arguments do not work when calling with function pointers

However, a function pointer parameter of a function can have a default value.