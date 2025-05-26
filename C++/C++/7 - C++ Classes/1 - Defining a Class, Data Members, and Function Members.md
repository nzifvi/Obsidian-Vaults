[[2 - Constructors and Destructors]] <- Next

---
## Defining a Class
The datatype, followed by the class name, is used to define a class.

```c++
class ClassName{

};
```

The class, ClassName, is now defined.

## Defining Data Members
Data members are essentially variables inside the class.
- Good practice to store data members in the private section of a class.

```c++
class ClassName{
private:
	int x;
	int y;
}
```

Can initialise data members inside of the class definition or via a constructor.

## Defining Member Functions
Function members are functions that belong to the class. They are used to operate on data members or parameters they receive when they are called.

```c++
class ClassName{
private:
	int x;
	int y;
public:
	void foo(int value);
	int getX();
}
```

Function members can either...

1) Be declared and defined within the class definition
```c++
class ClassName{
private:
	int x;
	int y;
public:
	void foo(int value){
		return x + value;
	}
	int getX(){
		return x;
	}
}
```

2) Be declared in the class definition and defined elsewhere.
```c++
class ClassName{
private:
	int x;
	int y;
public:
	void foo(int value);
	int getX();
}

ClassName::foo(int value){
	return x + value;
}

ClassName::getX(){
	return x;
}
```