[[3) self]] <- Back

---
## How to inherit
To make a class inherit from another do...
```python
class ParentClass:
	pass
	
	
class childClass(classToInheritFrom):
	

```

NOTE:
- Child class' constructor will override the parent's constructor if one is defined for the child.
- Can call the parent's constructor via the child's constructor

```python
class childClass(ParentClass):
	def __init__(var1, var2, var3):
		ParentClass.__init__(var1)
```

## super() function
The super() function is used to access a function member of the parent class: preventing it from being re-defined in the child class.
- Any re-definitions of a function in the child class will overwrite the definition from the parent class.