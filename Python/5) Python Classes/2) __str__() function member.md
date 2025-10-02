[[1) Python Classes]] <- Back
[[3) self]] <- Next

---
# What is the str function member?
str() function is another function member all classes will have. It defines how to handle the class being assigned to a string type variable.
- takes self as an argument when function is called. Self references the object it is being called with.

```python
class AClass:
	def __init__(var1, var2, var3):
		self.var1 = var1
		self.var2 = var2
		self.var3 = var3
	
	def __str__(self):
		reurn "put string here"
```