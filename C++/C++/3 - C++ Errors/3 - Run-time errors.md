[[2 - Link-time Errors]] <- Back
[[4 - Exceptions]] <- Next

---
## What are Run-time Errors?
If a program has no compile-time errors and no link-time errors, it'll execute.

Run-time errors are not caught by anything. It is up to the programmer to predict/test for them and then handle/prevent them.

Programs have to be tested.
- Variables should be tested for possibly assigned values that cause run-time errors.
	- And then that value(s) should then be prevented from becoming a possible value of that variable.

- Above also applies to function parameters when a value is passed via a function call as an argument.

### When handling an error
- Give a helpful error message, provide information as to what caused the error.
- Either handle the error in some way of terminate the program executing there and then.

### Where to deal with an error
FOR FUNCTIONS:
Handle the error in the callee, that is n the function the error causing value was passed to.

Do not deal with the error anywhere else.

FOR VARIABLES:
Handle the error after assignment.

## Error Reporting
Sometimes, instead of terminating a program in the event an error has occurred in a function, an error value can be returned.
- The error value acts as a signal for whatever called the function, and can be used to control what happens next.

## What might cause a Run-time Error?

1) Range Errors.
2) Bad Input.
3) Narrowing Errors.
4) Logic Errors.

NOT EVERYTHING! (Many more complex things can cause run-time errors).


### Range Errors
A range error can occur when handling some kind of collection of data. When going out of range of said collection, undefined behaviour can occur.
- Can access random memory.

Exceptions can be used to force the handling of range errors.


### Bad Input
When taking in input from keyboard, a sensor, or any other form of input (files, etc), bad input can potentially be received.
- Bad input can cause undefined behaviour in a program.

Input should be validated/sanitised before being used anywhere.
- Bad input can be flagged with exceptions after failing validation.
- Bad input can then be sanitised, or something else can be done, when a catch block begins execution upon an exception it's designed for being thrown.


### Narrowing Errors
A nasty kind of error is a narrowing error. It is when a value that is "too large" to fit in a variable is truncated.
- Data is lost.
- Exceptions can be used to prevent narrowing, upon an attempt to assign a larger data type to a smaller one is detected, an exception can be thrown.

### Logic Errors
A computer is essentially a very fast idiot. It does EXACTLY as it is told, to the word.
- If the program has block of code which does something incorrectly, the computer will execute it no matter what.

Incorrect formulas, incorrect indexing, incorrect conditionals can all cause logic errors.