[[1) Defining Functions in Python]] <- Back

---
## Python Function Return Types#
In Python, a function's return type is dynamic. A function can return an int, string, or any other data type.

```python
def getValues(arr):
	if arr == 0:
		return 1
	else if arr == 1:
		return "hello!"
	else
		return 1.1
```

The above function can return an int, string, or float data type all from one function. The return type is chosen dynamically each time the function is called.

## Function Type Hints
A type hint, ->, indicates what data type a function may return.
- It does not mean that the function can ONLY return those.
- Type hints help with readability and static type checking.


```python
def getMid(a, b) -> int:
	return a + b / 2
```

If a function is meant to return multiple data types, it is best to leave no type hint.

If a function is 100% known to only return 1 data type, a type hint can help with reading code and understanding it.
