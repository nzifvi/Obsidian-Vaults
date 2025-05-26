[[1,1) Files]] <- Back
[[1,3) File Writing]] <- Next

## File Class

File class is an abstracted reference of a file.

File class contains...
1) Path variable, representing file path.
2) File name variable, representing the name of a given file.

NOTE: Having a file object, for a given file, does not mean that a file exists or is available for IO operations.
- It just means a file object exists.
- The file intended to be loaded may not actually be accessible or even exist.

Certain methods may throw an Exception, some might be IOException or SecurityException:
- exists(), length(), canRead(), listFiles(), createNewFile() may throw Exceptions listed above or additional ones.


## Preparing to write File

FileWriter class used for writing to files.

```java
FileWriter fw1 = new FileWriter(File f); //For loading a File object.

FileWriter fw2 = new FileWriter(String str);
/*
    For loading a FileWriter object used to write to a file
    specified as a file path (string).
*/
```

In both cases, if successful, a is opened and [[1,3) File Writing]] begins next.

If this fails, an IOException is thrown. Possible reasons are...
1) Wrong permissions.
2) Invalid file location.
   (other reasons may exist)

