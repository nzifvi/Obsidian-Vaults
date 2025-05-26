[[1 - Input]] <- Back
[[3 - Types and Objects]] <- Next

---
## Variables
RECALL:
The memory addresses where data is stored are referred to as objects.
- The memory address, where data is stored, also has a data type that specifies what is stored there and how to interpret the data.

A named object is called a variable.

## Variable Declaration and Definition
Declaring a variable means to just state the data type and name of a variable.
- No value is initialised to the variable

```c++
int x;
```

Above...
- A variable x, of data type int, is declared.

Defining a variable means that a value is initialised to the variable.

```c++
int x = 4;
```

C++ Compiler remembers EVERY variable's data type and ensures that every variable is used in a way the assigned type can be.


## Initialisation vs Assignment
There is a difference between initialisation vs assignment, despite them both utilising the = operator.

Initialisation is when a variable is given it's initial (first ever) value.

Assignment is when a variable is given a new value.