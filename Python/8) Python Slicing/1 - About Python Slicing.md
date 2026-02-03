
---
# About Python Slicing
ANY Python sequence type data structure (lists, tuples, string, etc) can be sliced.

Slicing allows for elements of a sequence type data structure to be accessed from 1 given index to another given index.
- Works like a for loop, iterating over the sequence type data structure.
- Can be used to create/access subsequences of the data structure.

Slicing is important for data structures like numpy ndarrays: enabling easy access of elements in a multi dimensional array.

```python
array1 = [1, 2, 3, 4, 5, 6, 7, 8]
sugarray = array1[start:end:step]
```
- start controls what index to begin slicing from (INCLUSIVE).
	- If left blank, default start = 0 (start of sequence type data structure)
- end controls what index to stop slicing at (EXCLUSIVE).
	- If left blank, default end = len of data structure.
- step controls how to increment the index, further controlling what elements are included
	- If left blank, default step = 1 (all elements within range $[start, end[$ are included ) 

