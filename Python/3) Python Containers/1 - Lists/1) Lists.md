[[2) Accessing List Items]] <- Next

---
## Lists
Lists are used to store multiple items as a single variables, similar to arrays.

To assign a set of values to a list...
- Encase a set of values between square brackets.
- Each value must be separated by a comma.

```python
aList = [1, 2, 3]
```

To access items within a list, access them by index.

```python
print(aList[0])
```

```output
1
```

Can also define an empty list for passing empty lists to a function

```python
newList = []
```

## List Properties

#### 1) Lists are ordered.
Lists have a defined order and that does not change.
- If an item exists at index 0, it remains at index 0 UNLESS something is done that changes it.
- Requires an action to change.

#### 2) Lists are changeable
Lists are changeable. This means that items can be changed, added, and removed after the list has been created.

#### 3) Lists allow Duplicates
Since lists are indexed, and elements are accessed by an index, lists can have items with the same values as they exist independently within the list.

#### 4) Lists can contain different data types
A list does not have to have it's items all be type of data type. Items can differ in data type.

```python
aList = [1, "ah", 1.1, True]
```


## List Length
The length of a list can be given by the len() function with the list as an argument

```python
aList = [1, 10]
print(len(aList))
```

```output
2
```
