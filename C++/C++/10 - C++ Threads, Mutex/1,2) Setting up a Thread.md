[[1,1) How Threads Work in CPP]] <- Back
[[1,3) CPP Thread Methods]] <- Next

---
## Setting up a Thread

First, must include the thread header...
```c++
#include <thread>
```

In C++ a thread is an object that interfaces with threads in the OS kernel.

```c++
#include <thread>

void foo();

int main(){
	std::thread threadObjName(functionAssigned, (arguments to give
	functionAssigned));
}
```

When initialising a thread object, you give the following arguments to the constructor:
- the function to assign to the thread.
- arguments you want the function to act on.