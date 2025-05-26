[[3) Changing Items in List]] <- Back
[[5) Loops and Lists]] <- Next

---
## Removing from a List
When removing from a list, without using any form of index range to change items, 3 approaches exist.

### 1) Removing specified Item
remove() takes an argument, the value to remove from a list, and removes it from a list.

- If multiple occurrences of the same value exist in a list, remove() removes the first occurrence it finds.
- No index required.


```python
aList = [1, 2, 3, 4, 5]
aList.remove(3)
print(aList)
```

```output
[1, 2, 4, 5]
```

### 2) Removing a specified Index
pop() takes an argument, an integer index, and removes the item stored at that index.

- If NO index specified, pop() removes the item at the final accessible index.

```python
aList = [1, 2, 3, 4]
aList.pop(0)
print(aList)
```

```output
[2, 3, 4]
```

del keyword can also be used to remove an item at a specific index...

```python
aList = [1, 2, 3, 4]
del aList[0]
print(aList)
```

```output
[2, 3, 4]
```

### 3) Clearing a List
Clearing an entire list means that all items are removed. The list still exists but it is entirely empty (it has no items).

clear() method is used to do this.

```python
aList = [1, 2, 3, 4]
aList.clear()
print(aList)
```

```output
[]
```

del keyword can be used to clear a list also, no index is specified: just the name of the list.

```python
aList = [1, 2, 3, 4]
del aList
print(aList)
```

```output
[]
```
