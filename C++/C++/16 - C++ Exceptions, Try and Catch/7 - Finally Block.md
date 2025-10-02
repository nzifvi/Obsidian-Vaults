[[6 - Exception Specification]] <- Back
[[8 - Good Practice for Exception Handling in Programs]] <- Next

---
## What is a Finally Block?
A finally block is the third, and optional, block of a try-catch statement. It defines a sequence of statements that are to be executed after...
- A catch block finishes execution, unless a graceful crash occurs.
- A try block finishes execution WITHOUT throwing any exceptions.

A finally block is always executed, unless a catch block performs a graceful crash and terminates the program.


![[Pasted image 20250604144204.png]]

## What a finally block should be used for
1) Cleaning up resources
	- Deallocating memory that was allocated.
	- Closing files that were opened.
	 etc...