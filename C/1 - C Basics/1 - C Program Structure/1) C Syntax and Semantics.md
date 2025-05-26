[[2) Identifier Declaration Rules]] <- Next

---
## C Syntactical and Semantic Problem
Two aspects of a C program to be understood:
1) Syntactical aspects: how do we specify a program so the compiler understands it.
	- SYNTAX

2) Semantic aspects: what do we specify so that the program does what we want it to do.
	- SEMANTIC.
	- 3 different semantic aspects exist...
		1) Declarative parts (what things are).
		2) Definition of Objects (where things are).
		3) Statements (what things are supposed to do).


## C Syntax

### C Syntax Section

#### 1) Special Words
Special words are concepts, and features, that the C language imposes on the program. They cannot be changed.

Types of special words are...
1) Data types (int, char, void, A\[n]), etc.
2) Pre-processor statements (anything with a # before it usually).
3) Keywords (return, break, etc).

#### 2) Punctuation 
C uses several types of punctuation to structure the source code.
##### a) Brackets
Five kinds of brackets: {. . .}, (. . .), \[. . .], /*. . .\*/

Brackets group parts of the source code: ALWAYS come in pairs (opening and closing bracket).

< . . . > is usually rare, mostly used in # include pre-processor statements.

##### b) Separators
Sometimes, such as in function calls, the arguments MUST be separated. This is done by the use of commas.

```c
printf("%i\n%i\n%i", x, y, z)
//x, y, z are arguments of printf() function call, separated by commas.
```

##### c) Terminators
A terminator ; indicates the end of a statement. 
- EACH statement must have a ; at the end of it to indicate end of current statement.

#### 3) Literals
Literals are fixed values within the source code. These fixed values are constant and are never changed.

#### 4) Identifiers
Identifiers are names that a programmer, or the C standard, gives to entities within the program.

Identifiers can play different roles in programs.

Identifiers may refer to...
1) Data objects (A, i) that store some kind of value. Data objects are aka Variables.
2) Type, such as size_t, which specifies the sort of new object.
3) Functions, such as main() and printf().
4) Constants, such as EXIT_SUCCESS
#### 5) Functions
A function, such as printf() comes in 2 forms:
1) Function declaration.
	- Instructs the compiler that a function, with the given identifier, exists.
	- Instructs how many arguments there are, each being given an identifier.
	- Instructs the data type of each argument.
	- DOES NOT CONTAIN THE BODY OF THE FUNCTION.
2) Function definition.
	- The function definition is where the actual implementation of the function exists.

#### 6) Operators
C has numerous operators, a few are:
- = is for initialisation and assignment.
- < is for comparison (value a is less than value b).
- ++ is for incrementation.
- * is for multiplying two values.

### C Syntax Important Takeaways

1) ALL identifiers must be declared before they are used.

2) Identifiers only exist within the scope they are declared.

3) Declarations specify an identifier, where something can be assigned/initialised to said identifier later, NOT THE OBJECT OF AN IDENTIFIER NOR WHERE THE OBJECT CAN BE FOUND
	- The object an identifier refers to is achieved by definition.

4) An object is defined at the same time it is initialised
```c
int main(void){
	int x; //identifier x is declared.
	x = 4; //data object, of int 4, is defined and assigned identifier x.
}
```

5) EACH object, or function, must only have 1 definition.