[[5 - Catch Blocks]] <- Back
[[7 - Finally Block]] <- Next

---
## What is Exception Specification?
Exception specification is when a function declares whether it throws an exception or not at all.
- Done with the use of ```noexcept``` keyword appended to the function declaration AND definition.


### Declaring a function throws NO exceptions
```c++
void func() noexcept{
	// ...
}
```


### Declaring a function DOES throw exception(s)
```c++
void func() noexcept(false){
	// ...
}
```