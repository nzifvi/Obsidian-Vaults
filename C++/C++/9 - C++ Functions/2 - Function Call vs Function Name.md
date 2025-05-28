[[1 - How do Functions work in C++]] <- Back
[[3,1 - Function Pointers]] <- Next

---
## Function Call vs Function Name
When calling a function, using (), you perform a call: transferring execution to the function object which resides at that memory address.

```c++
int foo();

int main(){
	std::cout << foo(); // A function call
	std::cout << foo; // Something else
}

int foo(){
	return 5;
}
```

```output
5 (int)
1 (boolean)
```

By using the function name, as opposed to calling the function, C++ compiler converts the function name to a function pointer.
- the << operator doesn't know how to print a function pointer, therefore it converts it to a boolean.
- This is why 1 is printed in this case.