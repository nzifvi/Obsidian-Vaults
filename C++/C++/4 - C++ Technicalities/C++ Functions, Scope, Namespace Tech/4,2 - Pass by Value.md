[[4,1 - Function Call and Return]] <- Back

---
## Pass by Value
When passing a variable to a function, the simplest way of passing is known as pass-by-value.

Pass by value creates a local variable version of the passed variable.

ANY changes to that local variable only occur within that function scope. It does not alter the calling scope's version of the passed variable.

## Cost of Pass-By-Value
Since passing by value creates a copy, the entire passed variable must be copied.