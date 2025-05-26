[[3 - Scope]] <- Back
[[5 - Namespaces]] <- Next

---
## Function Call and Return
Functions are a way of representing actions and computations.

Whenever we want to do something that is an action, and worthy of a name, a function is created of it instead.

### Declaring Arguments and Return Type
A function declaration consists of a return type, followed by the function name, and a list of formal arguments in parentheses.
- Each argument MUST have a data type and name specified.

```c++
//FUNCTION DECLARATION
returnType funcName(dataType1 v1, dataType2 v2);

//FUNCTION DEFINITION
returnType funcName(dataType v1, dataType v2){

}

```

If a function returns a specific data type, let the return type be that data type.

If it returns nothing, let the returnType be void.
