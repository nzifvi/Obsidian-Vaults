[[1) Lists]] <- Back
[[3) Changing Items in List]] <- Next

---
## Accessing List Items
Lists are accessed like arrays, by an index.

However, Python Lists provide a lot of functionality that is already implemented by Python.

## 1) Negative Indexing
Negative indexing means to start from the END of a list. The index accessed, with negative indexing, would be a - b
- a is the final accessible index
- b is the negative index

```python
aList = [1, 100, 4, 8, 9]
print(aList[-0])
```

```output
9
```

As 4 - 0 = 4, aList\[4] is accessed

```python
print(aList[-1])
```

```output
8
```

As 4 - 1 = 3, aList\[3] is accessed

Be careful to ensure that |b|, absolute value of b, is not greater than a as you will actually access a negative index which causes an error.


## 2) Range of Indexes
A range of indexes can be specified. One index is the starting index and the other is the stopping index.

NOTE: the range is not stopping index inclusive. The range includes the previous index to the stopping index.

When specifying a range, the return value is a new list with items in the specified range.

Useful for creating sublists / partitioning lists.

```python
aList = ["apple", "orange", "grape", "banana", "dragon fruit", "kiwi"]

subList1 = aList[0:2]
subList2 = aList[2:len(aList)]

print(subList1)
print(subList2)
```

```output
['apple', 'orange']
['grape', 'banana', 'dragon fruit']
```

By excluding a starting index, the starting index defaults to 0 as any list, like an array, starts at index 0.

By excluding a stopping index, the stopping index defaults to the last accessible index of the list.

Negative indices can be used for both starting and stopping indexes if wanting to start from end of list instead of start of list.

## 3) Check if item in this list
A list can be checked to see if an item exists in a list, returning a Boolean value depending on if item is in the list.
- true if in list.
- false if not in list.

```python
aList = [1, 2, 3, 4, 5, 6]

if 1 in aList:
	print("1 is in the list")
else:
	print("1 is not in the list")
```