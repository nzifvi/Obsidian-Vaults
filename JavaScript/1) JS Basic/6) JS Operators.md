[[7) JS Functions]]
- In JS, like C and C++, operators can be understood in 3 groups:
1) Assignment operators.
2) Arithmetic operators.
3) Comparison operators.
4) String operators.
5) Logical operators.
6) Bitwise operators.
7) Ternary operators.
8) Type operators.

## 1) Assignment Operators:
- The assignment operator, =, assigns a value to a variable.
```
let x = 10; //Assignment operator assigns 10 to variable x.
```

- += adds a value to a variable.
- -= subtracts a value from a variable.
- asterisk= multiplies a value by a variable. REPLACE ASTERISK WITH AN ACTUAL ASTERISK
- /= divides a variable by a value.
## 2) Arithmetic Operators:

### 2.1) JS Addition and Subtraction:
- + used for addition.
- - used for subtraction.
### 2.2) JS Multiplication and Division:
- * used for multiplication.
- / used for division.

### 2.3) JS Modulus:
- % (modulus) returns the division's remainder.
```
let x = 20;
y = x % 2;
console.log(y);
```
OUTPUT:
```
0
```
### 2.4) Increment and Decrement
- Increment adds a value by 1. Decrement subtracts a value by 1.
- ++ is to increment.
- -- is to decrement.

## 3) Comparison Operators:

- == equal to
- === equal value and equal data type.
- != not equal
- !== not equal value or not equal type
- > greater than
- < less than
- >= greater than or equal to
- <= less than or equal to.
- < ternary operator.

## 4) String Operators:
### 4.1) String Comparison:
- All the comparison operators can be used on strings.
```
let str1 = "A";
let str2 = "B";
let result = text1 < text2;
```
- Strings are compared alphabetically. 

### 4.2) String Concatenation:
- Using the addition operator, strings can be concatendated:
```
let str1 = "John";
let str2 = "Doe";
let str3 = str1 + " " + str2;
```
- Using the += operator, a string can be concatenated to an existing string variable.
```
let text1 = "What a";
text1 += " shithole!";
```

### 4.3) Adding Strings and Numbers:
- Adding two numbers will return a sum. Adding a number and a string will return a string.
```
let x = 5 + 5; //AN INTEGER DATATYPE.
let y = "5" + 5; //A STRING DATATYPE.
```

## 5) Logical Operators:

- && logical AND.
- || logical OR.
- ! logical NOT.

- Logical operators can be used to chain multiple comparison evaluation. 
```
let x = 4;
let y = 10;
let numCheck = (x < 3) && (y == 10);
```
OUTPUT:
```
TRUE;
```

## 6) Typeof Operators:
- typeof returns the type of a variable.
- instanceof returns true IF an object is an instant of an object type.