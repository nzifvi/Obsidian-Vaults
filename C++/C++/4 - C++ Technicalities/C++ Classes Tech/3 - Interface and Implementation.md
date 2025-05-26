[[2 - Classes and Members]] <- Back
[[4 - Structs]] <- Next

---
## What is an Class Interface and Implementation?
A class has an interface plus implementation.

The interface is where the parts of a class's declaration can be accessed, by it's users, directly.
- The interface exists in the public section of a class.

The implementation part of a class is where parts of the class are used by the user indirectly THROUGH the interface.
- Data members found here.
- Function members, which a user does not need to interface with the class, are here too.


```c++
class AClass{
private:
	// IMPLEMENTATION SECTION
public:
	// INTERFACE SECTION
}
```