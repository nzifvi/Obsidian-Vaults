[[6,1) Scanning]] <- Back

---
## What is a Delimiter?
A Delimiter is specified as a regular expression, aka Pattern, which instructs a Scanner object how to scan the input.
- Characters used to define RegEx...

1) \\\s denotes a space, \\\d denotes a digit.
2) a character, without double \\, denotes that character.
3) * denotes zero or more times...

Examples:

![[Pasted image 20250327111631.png]]

Meaning: many spaces


## How does it work?
The methods Scanner provides, such as next(), nextInt(), return the String that comes between the current file position AND the next sequence that matches the Delimiter's currently loaded RegEx.
- nextLine() returns the String from position to end of line, regardless of RegEx...

```java
import java.util.Scanner;

public class Main{
	String input = "      hello ";
	try(
		Scanner scanner = new Scanner(input)
	){
		scanner.useDelimiter("\\*"); //load RegEx for Delimiter
		System.out.println(scanner.next());
	}catch(Exception e){
		//some debugging statements... or handle exception gracefully
		exit(1);
	}
}
```

OUTPUT:
```
h
```

The RegEx