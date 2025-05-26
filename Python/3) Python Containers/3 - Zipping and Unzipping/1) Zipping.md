[[2) Unzipping]] <- Next

---
## Zipping
You can zip n iterables together, returning a zip object.
- Iterables being lists, tuples, etc.

```python
aList = [1, 2, 3, 4, 5]
aTuple = ("John", "ohn", "hn" , "n", "")
zippedData = list(zip(aList, aTuple)
print(zippedData))
```

```output
[(1, "John"), (2, "ohn"), (3, "hn"), (4, "n"), (5, "")]
```

the zip constructor, zip(), returns a zip of tuples.
- zip is an iterator. The tuples a zip object contains can be iterated over.
- the size of the iterable being zipped, with the smallest number of elements, out of all iterables being zipped is when tuples stop being created
- Only zips as many tuples, with corresponding elements, that it can.

Because zip is lazy, it does not become a list of tuples by default. It is a zip object by default.
- To get a list of tuples, of the tuples that have been zipped, can either...
	1) Pass zip object to list constructor.
	2) Use list comprehension to return a list of the tuples (allows for conditionals to be used, some data  be filtered).


## Uses of Zipping

#### 1) Combining Related Data
Related data is often stored in different lists but corresponding indices.

```python
employeeNames = ["Jane", "Sandra", "Maurice"]
employeeSalaries = [24000, 48000, 12000]

print(employeeNames[0] + ", "+ employeeSalaries[0]) # index 0 is data for Jane
```

Instead, the 2 lists can be zipped together and the related data can be stored in tuples.
- Each tuple contains related data, determined by index of the lists being zipped.


```python
employeeNames = ["Jane", "Sandra", "Maurice"]
employeeSalaries = [24000, 48000, 12000]

employeeData = list(zip(employeeNames, employeeSalaries))

for employeeName, employeeSalary in employeeData:
	print(f"{employeeName} earns {employeeSalary}")
```