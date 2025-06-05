[[7 - Finally Block]] <- Back

---

### 1) Catch exceptions by reference and make them const.
Catching by reference ensures no additional memory is allocated.

Making the references to exceptions const prevents accidentally modifying them.

### 2) When handling an exception in a catch block, ensure resources are cleaned up if crashing gracefully.
An exception can be handled by 2 types of catch blocks.
- One which doesn't gracefully crash the program.
- One which does gracefully crash the program.

A catch block which gracefully crashes should deallocate memory, close files, and do whatever else must be done to shut down the program in a healthy way.

A catch block which does NOT gracefully crash the program should deallocate memory and close files which were all done within the function.
- Doesn't need to do it for the ENTIRE program, only the section the try-catch block exists in.

### 3) Do not group the handling of exceptions unless they all share a common solution/graceful crash

### 4) Do not use exceptions for regular control flow, ONLY use them in the event of an error.