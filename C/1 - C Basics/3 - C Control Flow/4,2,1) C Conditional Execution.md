[[4,1) C Control Flow]] <- Back
[[4,2,2) bool]] <- Next

---
## If
if statement allows for some kind of logical condition to be evaluated and, if the condition is true, the block attached to the if statement is executed.
- Controls program flow by ONLY allowing the block to be executed if the logical statement evaluates to true.

```c
int x = 3;
if(x == 1){
	//code block...
}
```

## else
else statement, attached to the end of else if, or just if, gives a code block to execute if ALL of the if and else if statements that came before evaluated to being false.

```c
int x = 3;
if(x == 1){
	//code block...
}else{
	//another code block...
}
```

## else if
else if statement allows multiple chains of if statements to be attached to the first if statement.
- Each has a logical condition, encased within parentheses, to be evaluated.
- Each has a code block nested within { }.

```c
if(x == 2){
	
}else if(x == 1){
	
}else{
	
}
```



## if, else-if, else statements vs blocks
Instead of an entire code block being attached to each condition, using { }, a single statement can be attached...

```c
if (x == 1) printf("x is 1");
else printf("x is not 1");
```

- ONLY GOOD IF A SINGULAR STATEMENT IS TO BE EXECUTED.

- CODE BLOCKS SHOULD BE USED FOR MULTI-LINE STATEMENTS.