[[1 - What are Templates]] <- Back

---
## Template Classes
A type parameter(s) can be specified for a class, making it a template class...

```c++
template<class T> class Example{
	T* array; 
	
	void insert(T arr, int pos);
	T remove(int pos);
	T& operator[](int n){return elem[n];}
}
```

Data members can have datatypes as type parameters, letting them be specified later.

Function members can have the datatype of a function member's return specified later.

Function members can have the datatypes of function parameters specified later.

When declaring an object variable of a template class, the datatype must be specified upon declaration.

```c++
Example<int> object1;
```

## Template Functions
A template function can be defined by doing...

```c++
template<class T> void func(T arr);
```

When calling the template function, the type parameter's datatype must be specified

```c++
func<int>(8);
```
