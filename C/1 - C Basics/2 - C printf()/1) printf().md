
---
## What is printf()
printf() is a function, from stdio.h library, that allows for an input string to be printed to console.
- Takes a string literal.

```c
#include <stdio.h>

int main(void){
	printf("hello");
	return 0;
}
```

```output
hello
```

## Using Escape Characters
Escape characters, which there are many of, each having a different outcome, allows for characters to be specified that otherwise are impossible to.
- Example: newline character, \n

Every escape character has a backslash, \\, at the start. It is then followed by a specific character.
- Each character provides a different modification to the string literal.

```c
#include <stdio.h>

int main(void){
	printf("hel\nlo")
	
	return 0;
}
```

```output
hel
lo
```

## Using Format Specifiers
If wanting to print values which are from variables, elements of an array, or something that is UNKNOWN DURING SPECIFYING THE STRING LITERAL, format specifiers can be used.
- A value is then inserted in place of the format specifier during compilation time.

```c
int main(void){
	int x = 3;
	printf("%i", x);
	//printf("% % %", identifier1, identifier2, identifier3)
}
```

```c
3
```

The order of the format specifiers, and the variables identifiers following, must correspond.
- The value inserted in the format specifier corresponds with the step of the sequence of variables identifiers outside the string literal.
- MUST have the same type.