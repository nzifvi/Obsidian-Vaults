[[3 - Access Specifiers]] <- Back
[[5,1 - Inheritance]] <- Next

---
## What are Friend Functions and Classes
A class, or function, being a friend of a class allows it to have access to private and protected data members and function members of a class.

Without, you can only access protected (if inherited) and public no matter what.

This is a type of privileged access and is NOT inheritance.
## Declaring and Defining Friend Function
A friend function is declared in a class. It is then defined outside of a class.

The friend function must also be passed an object variable, of the class it is a friend function of, in order to access the private and protected sections.

```c++
class A{
private:
	int x = 12;
public:
	friend void foo(const A& obj, int a);
}

void foo(const A& obj, int a){
	std::cout << obj.x + a << "\n";
}
```

That way the function is independent of the object but gets privileged access to the private and protected section.

Friend functions MUST be declared inside the class they are a friend of.

## Declaring and Defining a Friend Class
A friend class is a data member within a class.

When a class has a friend class, it allows for function members to access private and protected members of the friend class when they are given an object variable of that friend class.

Function members can only access the friend class' private and protected members when given a reference, or copy, of the friend class.

```c++
template<class T> class B; // forward class declaration

class A{
private:
	friend class B; // friend declaration, B is a friend of A
protected:
public:
	void* search(B& obj);
}


template<class T> class B{
private:
	T* array
	int size;
}
```

Friend class B does not mean a object variable of B exists in A, it is just a statement to treat B as a friend class of A.