[[2 - try-catch blocks]] <- Back
[[4.1 - Types of Exception]] <- Next

---
## How to Throw Exceptions
Exceptions can be thrown using the ```throw``` keyword, followed by the type of exception to throw...
```c++
throw ExceptionType;
```
Where ExceptionType is a valid type of Exception.

## How Throwing Exceptions Works
If a block of code throws an exception, it must be handled eventually. If it returns all the way to the main function, and is not handled there either, the program will crash ungracefully.

If a function throws an exception, execution stops immediately, and the block of code which called the exception throwing function has the option to handle it there.
- ADVICE: handle exceptions immediately otherwise multiple functions will terminate execution one by one as the exception goes up the call stack.

