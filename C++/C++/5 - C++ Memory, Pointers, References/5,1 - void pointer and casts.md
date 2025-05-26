[[4 - Pointers to Class objects]] <- Back
[[6 - References]] <- Next

---
## void* and casts
Sometimes, C++ has to get rid of the type system (a variable being of a specific data type).

This is because...
1) Sometimes, a C++ program must interact with another program which does not know about C++ types.
2) Old code, which does not use static types, must be interfaced with.

To achieve, the above... two things are required.
1) A type of pointer, that points to a memory address, without needing to know the data type of the object residing there.
	- Resolved with void pointers.

2) An operation that tells the C++ compiler what data type to assume an object is at a memory address of a pointer.
	- Resolved with static type casts.


## void*
A void pointer, void*, is a type of pointer that points to a memory address without knowing the data type of the object that resides there.

void* is used when transmitting an address between parts of a program.

```c++
void* ptrVar1 = new int; //int* converts to void*
```

When later using this pointer, the compiler must be told about the object's data type...
- Done with a static type cast.

## Type cast
A static_cast can be used to convert between data types, such as one type of pointer to another.
- static_cast is a dangerous operation, potentially violating type safety.
- static_cast aka explicit type conversion

```c++
void foo(void* ptr){
	int* ptrInt = static_cast<int*>(ptr);
	//ptr, declared as a void pointer, is casted to an int pointer
	// going onwards, it will be treated as a int pointer.
}
```

C++ offers 2 additional type casts, which can be even more dangerous.
1) reinterpret_cast
	- Can cast between unrelated data types, such as int to double*
	- Related types are data types which share the same function (an int and double are related as they store a number).
	- Unrelated types are data types which are used for different purposes. e.g. an int to a pointer.

2) const_cast
	- const_cast can remove a variable's const specifier.

There are both uses for reinterpret_cast and const_cast, seen in [[5,2 - reinterpret_cast and const_cast]] 