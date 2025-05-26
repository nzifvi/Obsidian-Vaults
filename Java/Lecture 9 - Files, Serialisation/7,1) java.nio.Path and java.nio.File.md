[[6,1) Scanning]] <- Back

---
## java.nio.Path

In java.nio package, there is an interface Path.
- For objects which describe a file.
- The class which implements Path will have to be structured based on the OS system the program is ran on.
- A factory class Paths can be used to create multiple Path objects from a String name.

## java.nio.File

In java.nio package, there is a Files class with static methods which operate on the filesystem.

Methods allow for creating files, opening files for reading or writing, copying files and more.

java.nio.File requires a Path to describe the file to operator on.