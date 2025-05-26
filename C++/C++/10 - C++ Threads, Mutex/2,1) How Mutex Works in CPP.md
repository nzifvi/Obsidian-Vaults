
---
## How Mutex Works in CPP
Mutex is a synchronisation tool that enforces only one thread, out of multiple, can access shared resources at a given time.
- Can apply a lock to an entire object by having a mutex be a non-static class variable.

To use mutexs, the mutex header must be included:
```c++
#include <mutex>
```

To lock a block of code, a mutex object must first be declared.

A thread acquires a lock, ensuring only that thread can access the mutex'd section of code at that time.
- Lock using std::mutex::lock() method.

Once the access to the shared resource section ends, use std::mutex::unlock() to release the lock, allowing another thread to now execute the mutex'd section of code.

Example below features locking off parts of a class:

```c++
#include <thread>
#include <mutex>

class A{
	private:
	std::mutex queueMutex;
	
	public:
	void foo(){
		queueMutex.lock();
		// continued method definition
		
		// shared resource accessing and or operations finished
		queueMutex.unlock();
	}
}
```

Now, whenever a thread calls the foo() method of an object, it locks it: preventing multiple threads from accessing it.

A function, independent of an object, can also be locked.

```c++
#include <thread>
#include <mutex>

void foo();

std::mutex fooMutex;

int main(){
	
	return 0;
}

void foo(){
	fooMutex.lock();
	// continued function definition
	
	// shared resource accessing and or operations finished
	fooMutex.unlock();
}
```