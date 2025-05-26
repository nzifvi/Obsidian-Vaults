[[2 - Constructors and Destructors]] <- Back
[[4 - Friend Functions and Classes]] <- Next

---
## What are Access Specifiers
Access specifiers create sections of a class that determine how the data members and function members, within the sections, can be accessed.

Three access specifiers exist:
1) private.
2) protected.
3) public.

To create a section, do...
```c++
class AClass{
private:
protected:
public:
}
```

### 1) private
A private access specifier means that ANY data members and function members within that section can only be accessed inside of the class.

- Data members are usually kept in the private section to ensure that they are not accidentally used elsewhere.

NOTE: when inheriting from a class, you cannot inherit it's private section.

Can circumvent this by using friend functions and classes
### 2) protected
A protected access specifier is like private, except that it can be inherited from.

The child class, inheriting a class's protected section, 

### 3) public
A public access specifier means that any data members and function members within that section can be accessed outside of the class, such as object variables of that class.

- Constructors and destructors must always be here.
- Function members can be here. They must be here if they are interfaces for a class.