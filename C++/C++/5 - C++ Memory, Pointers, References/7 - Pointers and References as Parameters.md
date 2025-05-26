[[6 - References]] <- Back
[[8 - The this Pointer]] <- Next

---
## Pointers as Parameters 
To declare a parameter to be a pointer...
```c++
void func(int* ptr);
```

Append the pointer operator, \*, on the end of the parameter's datatype desired to be a pointer.

When calling whatever uses the pointer parameter, pass it a pointer.

When a pointer is a parameter, it could potentially be null.
- Using a null pointer can lead to errors. Therefore, checks must be used to ensure the pointer is not null.

```c++
void func(int* ptr){
	if(ptr == 0){
		// Do something
	}else{
		// Continue with normal execution
	}
}
```

A null pointer is equal to 0.
## References as Parameters
To declare a parameter to be a reference...
```c++
void func(int& ref);
```

Append the address of operator, &, to the end of the data type of the parameter to be a reference.

References are interesting. A reference can BOTH be passed as a pointer parameter and as a reference parameter.

```c++
void func1(int* ptr);
void func2(int& ref);

int main(){
	int x = 42;
	func1(&x); //reference passed as pointer param
	func2(x); //variable passed as reference
}
```