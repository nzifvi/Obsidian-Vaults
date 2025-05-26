[[3 - Run-time errors]] <- Back

---
## What are Exceptions?
C++ provides a mechanism to help deal with errors: exceptions.

Idea of Exceptions:
- Separate the handling of an error, which is always done in the calling function.
- Whilst also ensuring that the detected error cannot be ignored.

Exceptions make handling errors easier and clearer.

If a function finds an error that it cannot handle, it does not return normally. It throws an exception.

When an exception is thrown, any direct (or in-direct) caller of that function can catch the exception.
- Catching the exception specifies what to do if the called function threw an exception.
- Occurs in the catch block of a try and catch statement.

The calling function will have a try block, which tries to execute some code. If anywhere in the code being tried, or any functions called from that try block, an exception is thrown, the catch block is jumped to.

```c++
int area(int a, int b);

int main(){
	try{
		int a = 1;
		int b = 2;
		std::cout << area(x, y);
	}catch(Bad_Area){
		std::cout << "negative length inputted\n";
	}
}

int area(int a, int b){
	if(a < 0 || b < 0){
		throw Bad_Area;
	}
	return a*b;
}
```