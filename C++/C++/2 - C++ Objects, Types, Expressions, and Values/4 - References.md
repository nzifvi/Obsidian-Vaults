[[3 - Objects]] <- Back
[[5 - Expressions]] <- Next

---
## What are References?
References are aliases: they are constant pointers for an object.
- References store the memory address of an object in memory.
- They DO NOT function like pointers.
- All operations using a reference are automatically dereferenced by the compiler.

References are...
1) immutable: their assigned memory address is constant and is not updated with another memory address.

## Binding a Reference to a Variable Object:
To assign a reference a value, you...
```
T& ref = x;
```
- Where x is a variable object, with type T.

A non-const reference means that the variable object referenced by a reference can be modified and that any modifications are reflected across an entire program.

a const reference means that it is read only. No modifications can be made but any modifications made to it are updated for the const reference.
```c++
const T& ref = x;
```

## Binding a Reference to a Temporary Object:
Because a temporary object CANNOT be modified(as it lacks a stable memory address), a temporary object can ONLY be referenced using a const reference.

```c++
const T& result = 1+3;
const T& refObject = box.get();
```

Binding a temporary object to a const reference means that it's lifetime is extended for as long as what references it remains in scope.

Once bound to a reference, a temporary object is addressable via it's reference.