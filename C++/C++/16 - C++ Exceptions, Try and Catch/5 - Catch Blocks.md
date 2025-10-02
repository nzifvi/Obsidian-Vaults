[[4.1 - Types of Exception]] <- Back
[[6 - Exception Specification]] <- Next

---
## Catch Blocks
Catch blocks go beyond just having a singular catch block which catches all types of exceptions.
- A try-catch block can have multiple catch blocks
- Can catch by value or by reference (like how function calls work with pass by value and reference).
- Can also perform polymorphic exception catches.

### Multiple Catch Blocks
Multiple catch blocks can be defined for a try-catch block. This is done for a block of code, in the try block, which can throw multiple types of exceptions.
- Each exception should be handled differently in an attempt to either save the program or let it crash gracefully.

```c++
try{

}catch(std::invalid_argument e){
	// Handle an invalid_argument exception
}catch(std::out_of_range e){
	// Handle an out_of_range exception
}
```

### Catch by Value & Catch by Reference
Catching a value results in a copy of an exception object being made upon the catch block, which handles that type of exception, beginning execution

```c++
try{
	// ...
}catch(std::invalid_argument e){
	// e is caught by value, thus it is a local copy.
}
```

- Doesn't impact anything, will still result in the correct catch statement beginning execution.

Catching by reference, like passing by reference for functions, means that...
- The memory address of the thrown exception is caught.
- No copy is made, saving time and memory.
- Passes a reference, and not a pointer.
	- A pointer has it's own memory address and occupies space on the stack.

```c++
try{
	// ...
}catch(std::invalid_argument& e){
	// e is caught by reference.
}
```

Catching by reference also has an additional feature however: polymorphic catches.

### Polymorphic Exception Catches
By catching by reference, you allow a catch block to catch an exception and all of it's child classes which are also exceptions.
