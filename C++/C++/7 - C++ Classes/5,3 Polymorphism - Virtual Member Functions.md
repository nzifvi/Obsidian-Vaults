[[5,2 - Initialising Base Classes in the Derived Class]] <- Back

---
## What is a Virtual Function?
A virtual function is a member function that is declared to be virtual in the base class.

A function member being virtual in a base class allows for any derived classes to override said virtual function, enabling different derived classes to have different behaviours for the same function.

For overridden classes...
- The parameters are the same.
- The return type is the same.

### Declaring/Defining a Virtual Function
```c++
class A{
private:
protected:
public:
	virtual void foo(){
		//function member body
	}
}
```

Virtual goes at the front of the function member declaration.

### Overriding virtual function in the derived class

Add override between the parameter list and the first brace of the member function's body to override it.

NOTE: CAN ONLY OVERRIDE FUNCTIONS DECLARED TO BE VIRTUAL IN THE BASE CLASS.

```c++
class A{
private:
protected:
public:
	virtual void foo(){
		//function member body
	}
}

class B: protected A{
private:
protected:
public:
	void foo() override {
		// new function member body.
	}
}
```


## How virtual functions and overriding works
Virtual functions enable runtime decision-making.
- Correct function, from the family of overridden functions of the virtual function, is executed based on the type of the object that it was called with.