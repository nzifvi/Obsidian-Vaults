[[2,3) CPP Mutex Methods]] <- Back
[[2,5) std lock_guard]] <- Next

---
## Locks and Exceptions
When the critical section is being executed, it is possible for an exception to be thrown.

RECALL: Once an exception occurs, the flow of execution is interrupted and control is swapped to the catch block.
- If a mutex was locked in the try block, it will never be unlocked.
- MUST unlock in the catch block and finally block.

Must ensure that all possible execution paths unlock the mutex before they finish executing.

```c++
#include <mutex>

std::mutex mtx;

// ...
mtx.lock() 
//mutex is locked, critical section is only accessible by current thread
// VV CRITICAL SECTION VV
try{
	// VV CRITICAL SECTION VV
	mtx.unlock();
} catch(){
	// VV CRITICAL SECTION VV
	
	//handle error
	mtx.unlock()
} finally{
	// VV CRITICAL SECTION VV
	mtx.unlock();
}
```