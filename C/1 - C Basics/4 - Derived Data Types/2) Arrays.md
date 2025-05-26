[[1) What are Derived Data Types]] <- Back
[[3) Pointers as Opaque Data Types]] <- Next

---
## Arrays
Arrays allow for group of objects, of the same base data type, to be grouped into an encapsulating object: an Array.

Arrays != pointers.
- Arrays look like pointers.
- Pointers refer to array objects.
- But they are not the same.


## Array Declaration
To declare an array...

```c
double A[4]; //An array, A, of 4 double data type elements.
```

An array ranges from 0 to n - 1, where n was the size the array was declared to be.
- n is the size of the array.

The data type of an array may itself be an array: forming multi-dimensional arrays.

```c
double A[M][N]; //An array of arrays of doubles.
//The array of arrays of doubles has a size of M.
//The arrays of doubles has a size N.

//Better notation exists to provide documentation...

double (B[M])[N];

//Either way, an array of the same type is declared.
```

## Types of Arrays
Two types of arrays exist in C:
1) Fixed length arrays.
2) Variable length arrays.

#### Properties of Arrays

1) Array length:
 The length of an array, A, can be given with...

```c++
double A[4];
int arraySize = (sizeof A) / (sizeof A[0]);
// size of array, in bytes, divided by size of array's elements data type.
```

NOTE: An array's length MUST be a positive integer value, or 0.
- If array's length = 0, there are no elements.

2) Can access an element, of an array A by...

```c++
int A[3];
A[0] = 1;
```

By \[x], where x is a valid index > 0 and < n - 1 (n = array length).
#### Fixed Length Arrays

#### Variable Length Arrays

## Array Takeaways

#### 1) Innermost dimension of an array parameter in a function is LOST.

#### 2) Do NOT use sizeof operator on array parameters inside functions. 

#### 3) Array parameters BEHAVE as if the array is passed by reference.
- Due to how arrays have an equivalent pointer form that the compiler treats arrays as.
## Strings
Strings are arrays of characters. However, the size of an array of characters, representing a string, must be handled carefully.

```char
char[5] = "hell"
```

Why 5? when...
A\[0] = "h", A\[1] = "e", A\[2] = "l", A\[3] = "l"?

Because an additional element must be used to store the null-byte terminator: \\0.
- Indicates end of string.
- String arrays must have size n + 1, where n = number of characters required for string.
- A\[n] stores the null-byte terminator.

Without a null-byte terminator, things can go wrong...

1) Long times for functions, operating on a string, because they do not find a null-byte terminator to end the string.
2) Segmentation violations as the functions, accessing a string, cannot find the end so they begin accessing random memory.
3) Random data corruption, throughout the program, because functions, operating on a string, write data in memory addresses where they are not supposed to.

