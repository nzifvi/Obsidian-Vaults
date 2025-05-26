[[1,3) File Writing]] <- Back

---

## File Reader
FileReader = a class which mirrors FileWriter.
- Instead of writing to a file, it is used to read from one.
- FileReader object requires the same three phase open, read, close pattern.

FileReader can only read a single character or a char array of pre-defined size.

FileReader cannot be informed how much data is in a file.
- Because something else might be writing simultaneously and, until it is read, it is unknown how much more will be added.

## Buffered Reader

BufferedReader class has a method called readLine()
- Method that allows processing strings.
- Can process entire rows of data.

NOTE: BufferedReader does not do file or file names.


## BufferedReader + FileReader
BufferedReader and FileReader can be used in tandem

```java
try(
	BufferedReader br = new BufferedReader(
		new FileReader(fileName)
	)
){
	String line = br.readLine();
	while(line != null){ //loop until line == null
		//process line
		line = br.readLine();
	}
}
```

If line == null, it signals end of stream.