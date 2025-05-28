[[2 - Function Call vs Function Name]] <- Back

---
## Function Pointer Syntax
To declare a function pointer...

```c++
functionReturnType (*ptrName)(parameters);
```

A function pointer can be reassigned to point to any function, in memory, that matches...
- The return type (functionReturnType).
- The specified parameters.

```c++
int foo1();
int foo2();
char foo3();

int main(){
	int (*ptrFunction)();
	
	ptrFunction = &foo1; 
	/*
	Doesn't error. Function matches the function
	pointer's
	*/
	ptrFunction = &foo2; 
	/*
	Doesn't error. Function matches the function
	pointer's
	*/
	ptrFunction = &foo3;
	/*
	Errors. foo3's return type is char whilst the
	function pointer's return type was specified
	as int.
	*/
}

int foo1(){

}

int foo2(){

}

char foo3(){

}
```

#### Const Function Pointers
To make a function pointer const do...
```c++
functionReturnType (*const ptrFunc)();
```

The pointer operator, \*, const.

## Specifying Parameters with a Function Pointer
To specify parameters of a function in a function pointer, only specify the datatype of said parameter.

```c++
functionReturnType (*ptrFunc)(int, int);
```
- Function pointer for functions which take 2 integer parameters and return a functionReturnType.

## Calling Functions assigned to a Function Pointer

Calling the function assigned to a function pointer can be done 1 of 2 ways.
1) Explicit Dereference.
2) Implicit Dereference.

#### 1) Explicit Dereference
In this method, you must dereference the function pointer in order to call the function object which resides at the memory address assigned to pointer.

```c++
int foo(int x);

int main(){
	int (*ptrFunc)(int) = &foo;
	std::cout << (*ptrFunc)(5);
}

int foo(int x){
	return x;
}
```

#### 2) Implicit Dereference
Implicit dereferencing functions as any regular function call does. Difference is the function pointer name is used instead of the function assigned to it.
- Compiler automatically handles dereferencing.

```c++
int foo(int x);

int main(){
	int (*ptrFunc)(int) = &foo;
	std::cout << ptrFunc(5);
}

int foo(int x){
	return x;
}
```

Compiler converts the implicit dereference version to the explicit one during compilation.