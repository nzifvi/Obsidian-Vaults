[[1) Opening and Closing Files]] <- Back

---
## How to Read files in Python
A file, once opened, can be read in multiple ways:
1) Entire file can be read in one go, using `read()` function
	- All contents become one large string.

```python
f = open(filePath)
fileContents = f.read()
```

2) Can read in a specific amount of characters from the file.
	- Done by providing a number of characters to read in as a argument during read() function call.

```python
f = open(filePath)
fileContents = f.read(amountToReadIn)
```

3) Can read in an entire line of the file (from starting character to newline character)
	- Done using `readline()` function member of file object.

