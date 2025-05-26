[[1,2) java.io.File]] <- Back
[[1,4) Reading Text from File]] <- Next

---

## File Writing

Once FileWriter initialised with a file, or file path, the file can be written to using several methods.

1) write(String s)
	- Write the String s to the file.

2) write(char[] cbuf, int offset, int length)
	- Write from the character array, cbuf, starting at cbuf[offset] for length characters.

Append methods exist to add content at the end of a file.

CAN throw an IOException.

Once done writing, .close() should be called.
- Flushes data to the file and releases OS resources for open files.
- If not closed, OS resources become tied up and, even if not using it, the resources are still allocated by OS.

.flush() method is also available to push to the disk without closing the file.
- Using sparingly.
- Generally, OS buffer management works okay-ish.

Above methods can also throw an IOException

## Example of Writing to file
```java
//suppose f is a fully initialised, working File object
FileWriter fw = new FileWriter(f);

while(moreToWrite){
    fw.write(next);
}

fw.close();
```