[[5,1 - void pointer and casts]] <- Back

---
## reinterpret_cast
A reinterpret_cast instructs the compiler that whatever is reinterpreted should be treated as this, regardless of if the data types share ANY similarity.
- Can be used to create a register on the heap.
- Why? Because a register must be able to take in ANY data type and perform an operation on it.

```c++
char* ptr = new char;  
*ptr = 'a';  
  
std::cout << *ptr;  
  
int* ptr2 = reinterpret_cast<int*>(ptr);  
*ptr2 = 10;  
std::cout << *ptr2;  
  

```

## const_cast
A const_cast removes the const off of a variable declared to be constant.

Can be used to unlock something and then lock it by casting it once more.

