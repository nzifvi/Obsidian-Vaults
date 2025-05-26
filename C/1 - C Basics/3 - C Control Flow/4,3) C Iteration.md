[[4,2,2) bool]] <- Back

---
## C for loop iteration
Using the for statement, a code block can be iterated over n times.
- Code block is re-executed n times.

```c
for(clause; condition; expression){
	//can have a code block
}

int x = 4
for(clause; condition; expression) x = x + 4;
//or just a singular statement
```

clause is where some iterator variable, with type int, is declared AND defined with an int value.
- The initial value of the iterator variable, i, is the starting value.

condition tests whether the iteration should continue, using some kind of logical condition.

expressions controls how the iterator variable should change in value EACH iteration of the loop.

