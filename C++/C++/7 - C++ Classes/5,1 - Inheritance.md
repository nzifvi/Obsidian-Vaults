[[4 - Friend Functions and Classes]] <- Back

---
## Inheritance
A class, A, can inherit from another class B

If this happens, class B is referred to as the base class.
- aka parent class

...and...

class A is referred to as a derived class of B.
- aka child class.

C++ inheritance causes the public and protected members of the base class to become available in one of the derived class's access specifier sections.
- Allows for control of access level.
- The private access specifier section of a base class will NEVER be inherited from.

### Inheritance Syntax

```c++
class A{
private:
protected:
public:
}

class B : inheritanceMode A{
private:
protected:
public:
}
```

### Inheritance Modes and their Results

##### inheritanceMode = public
```c++
class B : public A {
	
}
```

- Public data members of the base class become public in the derived class.
- Protected data members will become protected in the derived class.

##### inheritanceMode = protected
```c++
class B : protected A{

}
```

- Both public and protected members of the base class become protected in the derived class.

##### inheritanceMode = private
```c++
class B : private A{

}
```

- Both public and protected members of the base class become protected in the derived class.
- Private mode = default mode that is applied when no mode is specified

```c++
class B : A{ // default inheritance triggered 

}
```

## How C++ Inheritance Works
When a derived class inherits from a base class, the derived class receives a copy of the base class's non-static members.
- non-static members are inherited and embedded within B, kind of like being placed inside of the derived class.

Static members are not inherited by derived classes.
- Applies to both static data members and static function members.

Public and protected non-static data members are embedded into the derived class.

Public and protected non-static function members are also embedded.
- They are not overridden however, they have the same definition.
- To override an inherited non-static function, the non-static methods must be virtual in the base class.