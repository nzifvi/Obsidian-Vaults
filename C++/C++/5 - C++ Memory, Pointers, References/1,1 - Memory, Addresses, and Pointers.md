
---
## What is Memory?
A computer's memory is a sequence of bytes (8 bits). 
- EACH byte can be numbered from 0 to the very last one.
- The number used to identify a byte is referred to as a MEMORY ADDRESS.

![[Pasted image 20250517204254.png]]
(A MB of memory visualised)

Memory addresses are a kind of integer value.

ANYTHING put into memory has an address.

```c++
int var = 17;
```

The above declaration, and initialisation, of var results in an "int-sized" piece of memory being allocated, and the value initialised for var, being stored there.


## What is a Pointer?
A pointer is a variable which holds the memory address to something in memory.
- A pointer must be specific to the data type it points to in memory (if storing the memory address of an int in memory, must be an int pointer).
- Pointer datatype declared using an asterisk appended to the data type of the object in memory. 

```c++
int* ptr = &var;
```

The address of operator, &, is used to get the address of an object in memory.
- Then the address can be stored into a pointer variable with a corresponding data type

A pointer contains the memory address of an object in memory, to access the object, "contents of" operator, \*, is affixed to the front of the pointer.
- Contents of operator, \*, aka dereference operator. 

```c++
int x = 12;
int* ptrX = &x;
std::cout << *ptrX;
```

#### [[1,2 - sizeof operator]] <- Back