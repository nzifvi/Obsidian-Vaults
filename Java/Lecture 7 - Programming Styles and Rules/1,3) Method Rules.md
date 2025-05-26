---
Lecture7:
---

[[1,1) Good Programming Practices]] <- Back

---

RULES THAT APPLY WHEN CREATING METHODS:

1) Functions, aka methods, should be small.
	- Functions that are too large should be broken up into sub functions.

2) A function should do one thing, not multiple.
	- Makes it easier to debug and test.

3) Use a descriptive name that explains what the function is used to do.

4) Prefer fewer arguments, not mandatory though.

5) Have no side effects, unless it is clear what they are.
	- Should not randomly update a value outside of what the method returns, or operates on.
	- Can have a side effect but it should be obvious.

6) Do not use flag arguments.

```java
public void print(final int flag, final String arr){
    if(flag == 1){
        //do this
    }else if(flag == 2){
        // do this
    }
}
```

- Above code is bad practice. Instead, the method should be broken down into sub methods that perform the different behaviour the flag controls.

```java
public void printOnce(final String arr){
    //do this
}

public void printTwice(final String arr){
    //do this
}
```

- Avoids massive functions that can perform an unintended behaviour if the wrong value is somehow passed to it.
- Reduces size of methods.