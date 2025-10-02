[[6) Python File Handling, JSON/1) Python File Handling/2) Reading]] <- Next


---
## Opening Files
A file can be opened using the `open()` function with 3 parameters, 2 being optional.

```python
file = open(filePath, openMode, contentsMode)
```

- filePath is a string literal of the file path for the desired file to be opened.

- openMode is a string literal which controls what can be done with the opened file.
	1) "r"
		- Opens in READ mode (default mode).
		- Throws an error if file does not exist.
	2) "a"
		- Opens in APPEND mode: any new text written to file will be added to end of the current contents.
		- Creates file if the file attempted to be opened did not exist.
	3) "w"
		- Opens in WRITE mode: overwrites all content in given file.
		- Creates file if file attempted to be opened did not exist.
	4) "x"
		- Opens in CREATE mode: attempts to create the specified file at the specified file path.
		- Returns an error if the file exists within the given directory.

## Closing Files
Any file, once opened, should be closed when it is finished being used
- `close()` method used to close file.