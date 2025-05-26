[[2) Java Memory Model]] <- Back
[[3,1) Memory Use]] <- Next

---


![[Pasted image 20250411163416.png]]
## Common and Exclusive Memory
Two areas exist in Java Memory: Common and Exclusive Memory. The areas themselves contain further subareas. 

### Common Memory
Common Memory is a part of memory that is accessible by all threads.

It contains two areas: Method Area and Heap.

#### Method Area
Each class gets it's own area in the Method Area. Each reserved area, for each class, will have...

1) Runtime Constant Pool
	- Stores constants like Strings and symbolic references used by JVM.
	  
2) Method Code
	- This area of a classes' Method Area stores the bytecode of methods of the class.
	  
3) Attributes and Fields
	- This area of a classes' Method Area contains the metadata, field info, and methods info of the class.
	  
4) Class Info
	- This area of a classes' Method Area contains data about the class.
	- This could be the classes' parent, the classes' name, etc.

#### Heap
The Heap is used to store Objects and Arrays.
- All instances of classes, which are called Objects, are created here.
- The Heap is shared among all threads: any thread can access the Heap.


### Exclusive Memory
Each thread gets it's own private section of memory to prevent data interference between threads.

This private section of memory, for each thread, will contain...

1) PC Register.
	- Keeps track of current instruction being executed by the thread.
	- Each thread has own PC register because each thread may be executing different methods as some threads may run faster than others.
	  
2) JVM Stack.
	- Every method call performed by an individual thread gets it's own JVM stack.
		- 3 method calls means thread has 3 JVM stacks.
	- Each JVM stack contains...
	  
	1) Local Variables:
		- Values passed via method parameters and variables that have been declared locally within a method's scope.
		  
	2) Operand Stack:
		- Used for immediate calculations (like pushing and popping operands).
		  
	3) Frame Data:
		- Info for the method call and method return (example of info on method return is the return addresses of where to return to, in the bytecode, post method execution).
		  
3) Native Method Stack
	- 