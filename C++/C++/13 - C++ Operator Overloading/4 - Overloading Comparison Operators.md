[[3 - Example Usages for Operator Overloading]] <- Back

---
## Overloading Comparison Operators
Overloading comparison operators allows the comparison operators to be used to perform logical comparisons on user-defined objects (structs, classes, enums).

Example: can overload the == (equals) operator to check the equality between 2 user-defined classes in a specified way...

```c++
class Vector{
private:
	int xComponent;
	int yComponent;
	int zComponent;
public:
	Vector(int x, int y, int z){
		xComponent = x;
		yComponent = y;
		zComponent = z;
	}
}

bool operator==(const Vector& v1, const Vector& v2);

int main(){
	Vector v1(0, 0, 0);
	Vector v2(0, 0, 0);
	std::cout << v1 == v2;
}


bool operator==(const Vector& v1, const Vector& v2){
	return v1.getX() == v2.getX() &&
		   v1.getY() == v2.getY() &&
		   v1.getZ() == v2.getZ();
}
```

