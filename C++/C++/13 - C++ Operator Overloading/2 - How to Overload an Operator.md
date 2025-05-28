[[1 - What is Operator Overloading]] <- Back

---
## How to Overload an Operator
Using the ```operator``` keyword, an operator, such as +, can be overloaded to define a behaviour when given an exact set of parameters.

### Operator Overload Syntax
```c++
returnType operator_(parameters);
```
- To overload a given operator, append the desired symbol after the operator keyword.
- Specify the parameters of the operation.

```c++
struct Vector{
	int xComponent;
	int yComponent;
	int zComponent;
	Vector(int x, int y, int z){
		this->xComponent = x;
		this->yComponent = y;
		this->zComponent = z;
	}
};

Vector operator+(const Vector v1, const Vector v2){
	return Vector(
		v1.xComponent + v2.xComponent,
		v1.yComponent + v2.yComponent,
		v1.zComponent + v2.zComponent
	);
}

int main(){
	Vector v1(0, 0, 0);
	Vector v1(0, 0, 0);
	
	v2 = v2 + v1; // Calls the overloaded operator operator+(v1, v2)
}
```

Whenever an + operation is called, using 2 Vector objects, the user-defined operator overload is called.
