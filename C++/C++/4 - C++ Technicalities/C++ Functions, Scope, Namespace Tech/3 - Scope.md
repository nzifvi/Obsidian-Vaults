[[2 - Header Files]] <- Back
[[4,1 - Function Call and Return]] <- Next

---
## What is a Scope?
A scope is a region in a program, whatever is declared within that scope will only exist within that scope.

A scope exists from the moment it is declared until the moment it ends.

For the program...
```c++
void foo(){
	// Scope A
	{
		// Scope B
		{
			// Scope C
			{
				// Scope D
			}
		}	
	}
}
```

Anything declared in an outer scope will exist within an inner scope.

However, only things declared in an inner scope exist within that scope.

If something was declared in scope B, it would not be accessible in scope A.
- It would be accessible to ANY scopes nested in scope B however.


## Types of Scope
Multiple types of scope exist, allowing the use of names to be controlled.

1) Global scope: ANY area of the program outside any other scope.

2) Namespace scope: A named scope nested in the global scope or another namespace.

3) A class scope: the region within a class.

4) A local scope: a region of code between braces {}

5) A statement scope: a region of code within a for, if, else if statement.