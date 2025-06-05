[[1 - What are Exceptions]] <- Back
[[3 - Throwing Exceptions]] <- Next

---
## What are try-catch blocks?
A try-catch block is a structure which is used in exception handling.

### try section
The try block of a try-catch block attempts to execute a block of code. If an exception is thrown at any point within the try block, execution stops immediately at that line and execution control given to the catch block.

### catch section
The catch block of a try-catch block is used to catch the exception, hence catch as it's name.

The catch block should do one of two things.
- Attempt to fix what has gone wrong or define an alternative procedure of what to do in the event of something going wrong.
- Allow the thing the program controls to crash gracefully (stop operating in a peaceful, non-harmful way).
	- Examples: a train slows down and stops, a life support machine activates a backup, etc.

The type of exception, as well as what the program does, determines if the program can continue.
- If the exception is thrown due to something which is a mandatory dependency for the program to work, crash gracefully.
- Otherwise, a catch block would provide a workaround.

## Defining try-catch blocks
A basic try-catch block, without any additional catch blocks can be defined by...

```c++
try{
	// code to try...
}catch(ExceptionType& e){
	// what to do in the event of an exception of type ExceptionType occurs
}
```

Multiple catch blocks can be defined, each catching a specific exception type.
- Do rather than handling all exceptions in the same way. Some exceptions should be handled uniquely.