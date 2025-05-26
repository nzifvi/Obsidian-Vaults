[[3) Changing Items in List]] <- Back
[[5) Loops and Lists]] <- Next

---
## Adding to a List
Once a list is already declared, or assigned values, items can still be added to a list.

3 methods exist to add items to a list, without using changing and a range of indices.

### 1) Appending Items
append() method adds an item to the end of a list.

```python
aList[1, 2, 3, 4]
aList.append(5)
print(aList)
```

```output
[1, 2, 3, 4, 5]
```

### 2) Inserting Items
insert() method used to insert an item, at a given index, of a list.

Requires 2 arguments on call
1) position, aka index, to insert at.
2) item to insert

```python
aList = ["hello", "ben"]
aList.insert(1, "i am")
print(aList)
```

```output
["hello", "i am", "ben]
```

If inserting between 2 existing indices, or at the 0th position in a non-empty list, all items shifted to right by 1 and THEN the item is inserted at that index.

### 3) Extending Lists
extend() methods allows for the items of a list to be appended, one by one, from 0th index to last accessible index, to the end of an existing list.
- Takes a list, or some other iterable object, as an argument.

```python
list1 = [1, 2, 3, 4]
list2 = [1.1, 1.2, 1.3]

list1.extend(list2)
print(list1)
```

```output
[1, 2, 3, 4, 1.1, 1.2, 1.3]
```