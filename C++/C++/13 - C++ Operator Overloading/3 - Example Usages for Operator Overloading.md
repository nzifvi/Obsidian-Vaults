[[2 - How to Overload an Operator]] <- Back
[[4 - Overloading Comparison Operators]] <- Next

---
## Example Usages for Operator Overloading

#### 1) Improved array element accessing
Let the class Array exist.
- Class array acts as an interface between an actual array.

```c++
template<class T> class Array{
private:
	T* array;
	int size;
public:
	friend T operator()(int index);
}

T operator()(int index){
	if(index < 0 || index >= size){
		throw new IndexOutOfBoundsException;
	}else{
		return array[index];
	}
}
```

In this case, overloading the () operator has...
1) Given a way to validate an index is within bounds.


#### 2) Overloading I/O Operators
Overloading the i/o operators (<<, >>) allows for a custom behaviour to be defined when given a user-created object.
- Can define a custom behaviour for reading in a user-defined object, using std::cin.
- Can define a custom behaviour for printing out a user-define object, using std::cout.

 Suppose a class Vector exists.
 - If overloading the << operator, pass and return a reference to an ostream object.
 - If overloading the >> operator, pass and return a reference to an istream object.
 - If wanting to know about ostream, istream objects, look at

```c++
class Vector{
private:
	int xComponent;
	int yComponent;
	int zComponent;
public;
	friend std::ostream& operator<<(std::ostream& out, const Vector v);
}

std::ostream& operator<<(std::ostream& out, const Vector v){
	out << "[" << v1.xComponent << ", " << v1.yComponent << ", " << v1.zComponent 
	<< "]";
	return out;
}

int main(){
	Vector v(0, 0, 0);
	std::cout << v;
}
```

```output
[0, 0, 0]
```
