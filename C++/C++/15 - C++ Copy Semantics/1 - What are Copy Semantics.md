[[2,1 - Shallow Copy]] <- Next

---
## What are Copy Semantics?
Copy semantics allow for an object to be duplicated, one object is copied into another, resulting in 2 objects existing with the same values as their data members.

Requires a...
1) Copy constructor/assignment operator.

Can perform a shallow or deep copy:

## Copy Constructor
Any copy constructor must pass a reference, preferably a const reference (read only reference) to the object to copy from.

```c++
class AClass{
private:
	int* data;
private:
	AClass(const AClass& other){
		
	}
	
	~AClass(){
		// Destructor body
	}
}
```

The way the copy functions determines if a shallow or deep copy is performed.