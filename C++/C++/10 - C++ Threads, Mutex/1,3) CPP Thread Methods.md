[[1,2) Setting up a Thread]] <- Back

---

## CPP Thread Object Methods

### std::thread::join()
The join method blocks the calling thread from continuing execution UNTIL the thread that was joined finishes execution.

```c++
#include <thread>

void foo();

int main(){
	std::thread t1(foo);
	t1.join(); 
	// main will not continue execution beyond the join statement UNTIL 
	// t1 finishes executing
}
```

NON-STATIC METHOD, BELONGS TO A THREAD OBJECT POST-INITIALISATION.
### std::thread::detach()
The detach method separates the thread on the OS kernel from the thread object, allowing it to run independently from the calling thread. 

- A detached thread is a daemon thread, running the function the thread was assigned, before detachment, in the background

- Useful for when desiring for multiple parts of a program to run simultaneously (one to run a queue, one to manage an array, one to handle output to console, etc).

- Each thread can be assigned a part of a program and then detached to allow these processes to run in the background.

NON-STATIC METHOD, BELONGS TO A THREAD OBJECT POST-INITIALISATION.

### std::thread::hardware_concurrency()
Hardware_concurrency() is a method that returns the number of hardware threads. Can be used to determine how many threads to potentially create based on how many can execute concurrently.

STATIC METHOD, BELONGS TO THREAD CLASS AND IS NOT CALLED WITH A THREAD OBJECT.
### std::this_thread::sleep_for()
sleep_for(t) pauses the execution, of the thread, for t time.
- t = std::chrono::_\(t\)
- _ = period of time

After t time, the thread will begin execution again.