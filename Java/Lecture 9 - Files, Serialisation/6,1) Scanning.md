[[5) Structuring files]] <- Back

---
## What is Scanning?

Scanning = process of grouping individual characters, in the input, together into meaningful tokens.
- In text, whitespace might want to be recognised as a significant separator that means new word.
- New line symbol means to go to the next line of a file.
- Comma separated file means to treat next input as a new element.


Scanning != parsing. Scanning is about how to treat input and parsing is more about structure.

## Scanner
The Scanner class allows for the scanning process to be implemented.

Given a string, either from console or file input, Scanner can be used to separate a String into tokens based on a delimiter ([[6,2) Delimiter]]).

```java
String input = "1 fish 2 red fish blue fish";
Scanner s = new Scanner(input); //load string into Scanner...

s.useDelimiter("\\s*fish\\s*");

System.out.println(s.nextInt());
System.out.println(s.nextInt());
System.out.println(s.next());
Sysetm.out.println(s.next());

s.close();
```

Note: Scanner must have the same open, process, close pattern.