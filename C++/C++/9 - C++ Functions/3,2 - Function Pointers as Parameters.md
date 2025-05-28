[[3,1 - Function Pointers]] <- Back
[[3,3 - Important things to note about Function Pointers]] <- Next

---
## Function Pointers as Parameters
A function pointer can be a function's parameter and then later used within that function.

```c++
void getMax(int* array, int size){
	// suppose function gets the max value of an
	// array
}
```

In it's current form, the getMax function can only get the max value. To get the min value, another function would have to be made.

Using function pointers, it can be done all in one function.

```c++
void find(int array* int size, (*compare)(int, int));

void minCompare(int a, int b);
void maxCompare(int a, int b);

int main(){
	int max = find(intArray, 8, &maxCompare);
	int min = find(int array, 8, &minCompare):
}
```
## Why use Function Pointers as Parameters?
By using function pointers as parameters, code becomes more re-usable and less functions overall will need to be written to perform different types of behaviour.

- Code becomes more modular, allowing the behaviour of a function, using other functions, to be modifiable during runtime.

- Less functions written overall. For 3 functions which do only 1 thing different, you can instead write 1 function which does all 3 things.

