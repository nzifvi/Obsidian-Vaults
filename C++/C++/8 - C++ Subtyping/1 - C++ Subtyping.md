
---
## Subtyping in C++
In C++, subtyping is possible. That means that any of a base class's derived classes can be assigned to a variable of the base class.

Let B, C be derived classes of the base class A...
```c++
A* ptrA = new A();
B* ptrB = new B();
C* ptrC = new C();

ptrA = ptrB; // Valid, as B is a derived class of A

ptrA = new A();
ptrB = ptrA // Error, cannot assign a base class to a derived class pointer
```

Subtyping works best when using pointers. For example...

1) A vector, or array, of a base class and it's derived class.

```c++
std::vector<A*> vec;
vec.push_back(new A());
vec.push_back(new B());
vec.push_back(new C());

vec[0]->foo(); //A's version of foo() called
vec[1]->foo(); //B's version of foo() is called
vec[2]->foo(); //C's versiono of foo() is called
```

When subtyping with pointers, no casting is required.

Without using pointers for subtyping, in the above example, each foo() call would result in A's version being called.