[[1) C Syntax and Semantics]] <- Back

---
## Identifier Declaration Rules

#### 1) Type qualifiers (const, \*, data types), are on the LEFT of the identifer.
	- C Syntax reads from right to left.

```c
char* c;
//read as: c is a pointer to a char
```

- Type modifiers (unsigned/signed, const, volatile, etc) and pointer syntax ONLY binds to the identifier they correspond with...

```c
char* a,b;
//b is a char
// a is a pointer to a char
//BOTH ARE NOT POINTERS TO A CHAR
```

```c
char const* const path_name;
//path name is a const pointer to a const char
```

#### 2) Continued declarations are forbidden
A continued declaration is where multiple identifiers are declared in the same statement.
- Causes confusion about data types.

```c
char* a,b; //CONTINUED DECLARATION. BAD

//Doing the same, without continued declaration...
char* a;
char b;
```

#### 3) Array Form Notation should be used in place of Pointer Form notation when arrays are function parameters


In C, function parameters declared to be arrays (char string\[]) are ACTUALLY treated as pointers (char* string).
- The two can be used interchangeably.

Each notation has an equivalent array and pointer form.

Where possible, array form should be used instead of pointer form as the array form can provide enforced conditions on array arguments during function calls by compiler AND readability/documentation for array parameters.

##### a) Basic Array Notation:

To declare a basic array, with no kind of specifications, as a function's parameter...


```c
void printArray(int arr[], int size); //ARRAY FORM

void printArray(int* arr, int size)); //POINTER FORM
```

##### b) Fixed-Size Array

```c
void processorBuffer(char buf[256]); //Array form

void processorBuffer(char* buf); //Pointer form
```

In the array form of notation, an array size (number of elements) can be specified.
- This STATES the function expects an array, of the given data object, with the specified size.
- HOWEVER, the compiler does not enforce this. One even larger can be passed.
- The array form of the "fixed-size" is for readability/documentation.

##### c) Non-Null Pointer with Minimum Size
Using the static keyword, a minimum size of an array parameter can be enforced.

```c
size_t strlen(char str[static n]); //Array form

size_t strlen(char* str); //Pointer form
```

The array form allows for the array's size to be forced to be a minimum value n.
- Using static keyword.

For example...

```c
size_t strlen(char str[static 1]); //Array form
```

The array form of the str array parameter enforces that function calls of strlen() are given an array with at least ONE element.

##### d) Variable Length Array Parameters

```c
void matrixMultiply(int rows, int cols, int mat[rows][cols]); //Array form

void matrixMultiply(int rows, int cols, int (*mat)[cols]); //Pointer form
```

The array form of variable length arrays allows for dimensions to be clarified better than the pointer form.
- Pointer form is an equivalent array BUT harder to read.

##### e) Null-Byte terminated arrays
Usually apply to char arrays.

```c
int main(int argc, char *argv[argc + 1]); //Array form

int main(int argc, char **argv); //Pointer form
```

In the array form of argv...
- \[argc + 1] documents that the argv array has argc elements and a NULL terminator (denoted by + 1).

Pointer form, char **argv, is conventional but provides less information.

#### 4) Function form should be used instead of Pointer form when functions are parameters of functions.

ANY function, as a parameter of another function, has 2 forms: a function form and a pointer form.

```c
int atExit(void handler(void)); //Function form

int atExit(void (*handler)(void)); //Pointer form
```

When functions are parameters of another function, they are treated as function pointers.
- By using function form, instead of directly using pointer form, additional information can be given.

#### 5) Variables are defined close to their first use.