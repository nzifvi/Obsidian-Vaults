[[8.1) JS Objects]]
- Functions are blocks of code, which only exist inside that block, that are designed to perform tasks.
	- Like C/C++, a function is only executed when it is called.
	- Functions can ALSO return a value.

- Functions can be reused an infinite number of times. They save you writing a block of code many times.
- Functions can also return, or perform different actions, based on parameters.

## JS Function Syntax:
- To define a function, the function keyword is used.
- name of function follows.
- finally the parentheses, (), appended to the function's name

```
function functionName(parameter1, parameter2){

}
```
- In JS, unlike C/C++, the variable of parameters does not need to be specified. 

- Like C/C++, anything which occurs within the function is LOCAL to the block scope. 
	- Can return values to return an output of the function's statements.

## Function Invocation:
- The function is executed when something calls the function.
1) An event occurs (user clicks a button).
2) When it is called from the code.
3) Automatically (self called).

## Function Return:
- When a function reaches a return statement, the function will not execute beyond that point.
- the return keyword is used to return something.

## The () Operator:
- The () operator, in tandem with the name of the function, is used to call the function in the js code.

```
function toCelsius(fahrenheit) {
	return (5/9) * (fahrenheit-32);
}

let value = toCelsius(77);
```