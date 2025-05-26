[[4 - Structs]] <- Back

---
## What are Helper Functions?
Class interfaces should be kept to a minimum. Any operation that directly operates on the class should only be there.

A class representing a vector could be...
```c++
class Vector{
private: // Implementation
	double xComponent;
	double yComponent;
	double zComponent;
public: // Interface
	Vector(x, y, z){
		xComponent = x;
		yComponent = y;
		zComponent = z;
	}
	
	double magnitude();
	
	double xzPlaneAngle();
	
	double yzPlaneAngle();
	
	double xyPlaneAngle();
}
```

These, and a few more, function members are directly related to the class. However, some additional ones such as...

- One that computes the reflection, across an axis, of a vector.
- One that checks if 1 vector object is equal to another vector object.
- One that computes the coordinate of the head of the vector, returning it.

These are not directly related to a Vector, however, they have a function. These can be defined as HELPER FUNCTIONS.
- Helper functions aka auxilliary functions

```c++
class Vector{
// Vector class body...
}

void reflect(char axis){...}

bool operator==(const Vector& v1, const Vector& v2){...}

Coordinate headCoordinate(Vector v1){...}
```

To further increase the quality of this code, put it all into a name space.
- Related classes, and related auxiliary functions, should be in a name space.
- The namespace should have a name which identifies some common trait between all of the classes and auxiliary functions.

```c++
namespace LinearAlgebra{
	struct Coordinate{...};
	class Vector{...}
	
	namespace VectorAuxilliary{
		void reflect(char axis){...}
		bool operator==(const Vector& v1, const Vector& v2){...}
		Coordinate headCoordinate(Vector v1){...}
	}
}
```