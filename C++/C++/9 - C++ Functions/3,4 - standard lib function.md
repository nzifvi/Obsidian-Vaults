[[3,3 - Important things to note about Function Pointers]] <- Back

---
## std::function
std::function is a class which provides an alternative method to defining, storing, and later calling a function.
- part of the \<functional> header
- part of standard library, hence std namespace.

## Initialising a Function Object
```c++
#include <functional>
int foo();

int main(){
	std::function<returnType(parameters)> fcnPtr{&functionName};
}
```

NOTE: The function assigned to a function object MUST match the...
- Return type the function object was specified to have in initialisation.
- Parameter list, and types of parameters, the function object was specified to have in initialisation.
## Calling Function assigned to Function Object
To call a function assigned to function object, call it as you would any other function (using () after it's name) using the function object's name.
```c++
int foo();

int main(){
	std::function<int()> ptrFunc{&foo};
	ptrFunc();
}
```