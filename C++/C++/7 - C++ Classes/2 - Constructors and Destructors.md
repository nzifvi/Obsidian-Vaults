[[1 - Defining a Class, Data Members, and Function Members]] <- Back
[[3 - Access Specifiers]] <- Next

---
## C++ Constructors
Constructors are a type of function that are automatically called upon an object variable, of that class, being initialised.

Constructors are used to set up the class, initialising values or calling other functions that are involved in the initialisation of the object variable of that class.

### Declaring a Constructor
To declare a constructor, omit any datatype and just have the name of the class...

```c++
class AClass{
	private:
	protected:
	public:
	AClass();
}
```

Can pass parameters to the constructor.

NOTE: Constructors must be in the public section of a class as they must be accessed outside of the class.


## C++ Destructors
Destructors are automatically called when an object variable of a class goes out of scope.

They are used to handle "shutting down" the object variable, such as deallocating memory that was allocated to the heap to prevent memory leaks.

### Declaring a Destructor
To declare a destructor, do the same as how to declare a constructor, and affix a tilde, ~, to the front of the destructor name.

```c++
class AClass{
	private:
	protected:
	public:
	~AClass();
}
```