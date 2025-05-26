[[5,2 - Initialising Base Classes in the Derived Class]] <- Back

---
## What is a const Function Member?
A const member function ensures that any derived classes cannot override the const member function.

Function members declared to be const in a base class cannot be overridden by any derived classes.

```c++
class A{
private:
	int value;
public:
	int getValue() const {
		return value;
	}
}
```

const goes between the parameter list and the first brace of the function member's body.
- Same place as virtual.

## Consequences of a Function Member being const
A const function member CANNOT modify the current object (this).
- Cannot change any data member values.
- This can be circumvented using the mutable operator.


## mutable
mutable allows a data member of a class to be modified even inside of a const function member.

```c++
class A{
private:
	mutable int counter;
public:
	B* read(std::string filePath) const {
		counter++;
		//rest of function definition
	}
}

class B{
	//class definition
}
```

By declaring the data member to be mutable, it allows const function members to modify it.
- Useful for logging/caching.
- Only use mutable to bypass const function members when logging/caching.