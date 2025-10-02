[[1 - What are Move Semantics]] <- Back

---
## Move Constructors
A move constructor can be declared and defined as...
```c++
class AClass{
private:
	A* data;
	std::vector<B> vector;
	B& ref;
	C nonMoveableData;
public:
	AClass(AClass&& other):
	ref(other.ref),
	data(std::move(other.data)),
	vector(std::move(other.vector)),
	nonMoveableData(other.nonMoveableData)
	{
		other.data = nullptr; // transfer ownership of memory
	}
}
```

To ensure all data is moved and the ownership of memory is transferred, assign the other user-defined data types which are dynamically allocated a nullptr.
- stdlib class-types handle that themselves on a move operation.
## Moving Class-Type objects
Once a move constructor is declared and defined for a class, it can be moved using the std::move() function.
- std::move() function calls a move constructor and assigns the value of the expression to something (lvalue or reference).

Example:
```c++
AClass a("hello";
AClass b = std::move(a); // moved
```

