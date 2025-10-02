[[2 - Move Constructors and Moving]] <- Next

---
## What are Move Semantics in C++
Move semantics allows for the resources allocated to an object in memory, either dynamically (at runtime) or statically (by compiler), to be moved from one object to another instead of copying them.
- By moving, performance is saved.
- Very good for large objects.

Copying duplicates resources, which can be costly.

Moving transfers ownership of resources, leaving the original object (the one moved from) in memory but with it's contents empty.
- Copying just duplicates the values.

## How Move Semantics work in C++
Move semantics work by:
1) rvalue references (T&&) to identify an object of type T that can be moved from.
2) move constructors and move assignment operators to move the resources.
3) std::move() function 
	- move() casts an lvalue to an xvalue to enable moving.

Any class-type data members should be moved.
- Requires a move constructor for that class-type member.

Any data members which are pointers should be moved.

ANY non-moveable data member must be copied or handled some other way.
- Same applies to references, the memory address is copied over. It cannot be moved.