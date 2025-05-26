[[2) Accessing Tuple Items]] <- Next

---
## What are Tuples?
Tuples are used to store multiple items into a single variable.
- Tuples are ordered and unchangeable.

Ordered:
	The order the items are assigned in are how they must be accessed by index when accessing the items in the tuple later.


Unchangeable:
	Once items are assigned to the tuple, they cannot be changed AND items cannot be added/removed to/from the tuple.

```python
aTuple = (1, 2) # x, y coordinate as a tuple
```

## Properties of Tuples
1) A tuple's items do not have to be congruent data types. The items' data types can differ.

```python
aTuple = (1, True)
```

2) Length of a tuple, how many items it contains, can be given using len() function and passing tuple as an argument.

```python
aTuple = (0, 1, 4) #x,z,y coordinate
print(len(aTuple))
```

```output
3
```
