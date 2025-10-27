[[2) Python Function Return Types]] <- Back

---
# Function Arguments
Data can be passed to functions as arguments.
- Arguments specified in parentheses. Each argument separated by a comma.

```python
def func(arg1, arg2, arg3, arg4):
	# function definition
```


## Arbitrary Arguments
If it is unknown how many arguments will be passed to a function, an arbitrary argument can be used
- Affix asterisk, \*, to front of arg.

```python
def func(*people):
	if(len(people) < 1):
		print("not enough people")
	else:
		print(people[1])
```

The function receives a tuple of arguments as a parameter.


## Positional Arguments
Positional arguments are the default way a function is called. The value of a parameter depends on the order in which arguments were given to the function call.
## Keyword Arguments
When calling an argument, you can define the arguments as keys and assign them a value.

```python
def func(person1, person2, person3):
	print(person1 + person2 + person3)

func("bill", "bob", "nob")
```

```output 
billbobnob
```

If using keyword arguments, the order values are assigned to arguments is not important anymore.
- All that matters is the value

```python
func(person3 = "nob", person2 = "bob", person1 = "bill")

func(person2 = "bob", person1 = "bill", person3 = "nob")

```

```output
billbobnob
billbobnob
```

Just use the name of the argument and assign it a value.

## Default Parameter Value

A function's parameter can be assigned a default value in the event that the function is called without any input.

This can
- Be done to return a value in the event the function must return something to prevent errors.

```python
def getError(var1 = 0):
	return var1 * 4 
```

If the function is called, without giving it any arguments, the parameter will use the default value.

```python
	getError()
```

```output
0
```

If the function is called, and an argument is given, the value overwrites the default value of the parameter and is used in the function.
```python
getError(1)
```

```output
4
```

# Specifying Datatypes of Function Parameters
The datatype of a function's parameters can be specified. It follows a different syntax from C/C++

```python
def func(a: datatypeOfA, b: dataTypeOfB):
	# function definition here
```

If a parameter is assigned a different datatype than the one specified, a TypeError exception is thrown.
- Ensures functions are used correctly.