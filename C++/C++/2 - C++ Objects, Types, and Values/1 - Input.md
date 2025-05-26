[[2 - Variables]] <- Next

---
## Input
Taking input, from a stream, requires somewhere to store the value.

This "somewhere" is referred to as an object.
- An object is a region of memory with a DATATYPE that specifies what kind of information that can be stored in that region of memory.

A named object is referred to as a variable.

When assigning an input to a variable, the input must be of the same data type to the variable's specified data type.
- Can potentially type cast the input to be the data type of the variable.

```c++
string firstName; //variable of type string declared.
std::cin >> firstName; //input is assigned to the variable.
```

std::cin, from the iostream library, takes in user input from the console and assigns it to a variable.

When using std::cin, the computer will only take whatever has been inputted upon newline (enter key) being added to the input.
- When the input is sent to the program, the newline operator is not added to the variable.
