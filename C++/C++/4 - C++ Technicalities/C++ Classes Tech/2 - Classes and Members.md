[[1 - User Defined Types]] <- Back
[[3 - Interface and Implementation]] <- Next

---
## Classes and Members
Classes are a user-defined type. It is composed of multiple built-in types(strings, etc), other user-defined types, and functions.

The parts, used to define the class, are called members.
- Variables and functions part of a class are members of that class.

A class has zero, or more, members.

```c++
class AClass{
	private:
	int x; // data member
	int sum(int a, int b){ //function member
		return a + b;
	}
}
```

Members can be one of many types: most are either...
1) Data Members
	- Data members define the representation of an object of the class.
2) Function Members
	- Function members provide operations that can be performed on objects of the class.