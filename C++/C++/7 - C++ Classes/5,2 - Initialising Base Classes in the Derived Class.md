[[5,1 - Inheritance]] <- Back

---
## Initialising Base Classes in the Derived Class
A derived class must initialise the base class via the base classes constructor.

To do this, the derived class must call the base class's constructor

```c++
class A{
protected:
	int x;
public:
	A(int x){
		this->x = x;
	}
}

class B{
protected:
	int y;
public:
	B(int x, int y): A(x){
		this->y = y;
	}
}
```

After the constructor's parameter, use a colon and then call the constructor of the base class.
- Pass required arguments into the constructor.
- Must be between the final parenthesis of the derived class's parameters and the first brace of the constructor definition.

An inherited function member can be overridden, given that in the base class that function member is virtual
