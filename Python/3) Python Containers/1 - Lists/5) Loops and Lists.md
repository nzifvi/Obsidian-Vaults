[[4,1) Adding to a List]] <- Back
[[4,2) Removing from a List]] <- Back
[[6) List Comprehension]] <- Next

---
## Loops and Lists
A list can be looped through, accessing each item, in different ways. Multiple methods exist to loop through and each has a reason to use it.

### 1) For-each loop
Using a for each loop allows a copy of an item to be created per iteration. This item is interacted through it's copy.

```python
aList = [1, 2, 3, 4]
sum = 0

for x in aList:
	sum += x
print(sum)
```

### 2) For loop with index
Can also loop through a list by index using a for or while loop. 

- range() and len() functions used to create the for loop

```python
aList = [1, 2, 3, 4]
for i in range(len(aList)):
	print(aList[i])
```

Can be useful for methods which want to return, or operate on, indices.


### 3) While loops with index.
While loops allow multiple conditions to be true, such as whilst an index is less than the length of the list and another condition is not true.

- only the len() function needed, range() and len() only needed for for loops.

```python
aList = [1, 2, 3, 4, 5, 6]
i = 0 # need starting index outside while loop
while i < len(aList):
	print(aList[i])
	i++ # incrementation of index must be done by programmer
```

### 4) Looping via List Comprehension
List comprehension can be done to loop through a list.

```python
aList = [1, 2, 3, 4, 5, 6]
[print(x) for x in aList]
```

```output
1
2
3
4
5
6
```

