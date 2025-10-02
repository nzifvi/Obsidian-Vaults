[[1 - Defining a Class, Data Members, and Function Members]] <- Back
[[3 - Access Specifiers]] <- Next

---
## C++ Constructors
Constructors are a type of function that are automatically called upon an object variable, of that class, being initialised.

Constructors are used to set up the class and create a class-type object of it in memory. A constructor has two parts: it's initialiser and it's body.


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

### Defining a Constructor
Recall, a constructor has two parts:
- initialiser list.
- body

```c++
AClass(): initialiserList {
	// constructor body
}
```

#### Initialiser List:
The initialiser list executes BEFORE the constructor of the body does. References or consts must be initialised in the initialiser list BEFORE anything is done with them in the body.

All data members of a class should be initialised using the constructor's initialiser list.
- References or consts must be initialised in the initialiser list.
- Class-types should be initialised in the initialiser list for efficiency and standardisation.
- Built-in types can be initialised either in the initialiser list OR in the body. Do it in the initialiser list for standardisation.

#### Constructor Body:
The body is used for work that cannot be done in the initialiser list.
- Sometimes initialiser is enough.
- The body is what allows for...
	1) Logic and validation.
	2) Re-assignments to already initialised data members.
	3) Perform internal initialisation (initialisation which doesn't come from outside the class-type object (loading of files, booting of devices, etc that the class-type object handles)).

Example:
```c++
	AClass(MyClass&& other):
	ref(other.ref),
	data(std::move(other.data)),
	vector(std::move(other.vector)),
	nonMoveableData(other.nonMoveableData)
	{
		
	}
```

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