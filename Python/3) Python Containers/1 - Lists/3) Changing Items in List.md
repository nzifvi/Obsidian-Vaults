[[2) Accessing List Items]] <- Back
[[4,1) Adding to a List]] <- Next
[[4,2) Removing from a List]] <- Next

---
## Changing Items in List
To change an item at a given index, the index must exist.

An item in the list can be changed by referring to it's index and assigning the list, at that index, the new value

```python
aList = [1, 2, 3]
aList[0] = 10
print(aList)
```

```output
[10, 2, 3]
```

A range of items can be changed using an index range

```python
aList = [1, 2, 3, 4, 5, 6, 7, 8]
aList[:4] = [10, 11, 12, 8]
print(aList)
```

```output
[10, 11, 12, 8, 5, 6, 7, 8]
```

However, using a range comes at a catch.

If you insert MORE items than the range specifies to replace, the replacing items are inserted, linearly, one by one at the end of the upper bound - 1.
- All items after, which were there before, shift to the right by one

```python
aList = [1, 2, 3, 4, 5, 6]
aList[:2] = ["hello", "i", "am", "ahhh"]
print(aList)
```

```output
["hello", "i", "am" "ahhh", 3, 4, 5, 6]
```

The items, which were able to be overwritten whilst the index was in bounds, are overwritten though.

If you insert LESS items than the upper bound specifies are to be changed, then, once the items overwrite existing elements, all others are deleted UNTIL the upper bound is hit.
- Data is lost.

```python
aList = [1, 2, 3, 4, 5, 6, 7]
aList[:3] = ["hello"]
print(aList)
```

```output
["hello", 4, 5, 6, 7]
```

3 was lost
