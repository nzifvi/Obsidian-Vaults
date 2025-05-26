[[2,4) Locks and Exceptions]] <- Back

---
## What is std::lock_guard?
std::lock_guard is a C++ standard library class which automatically manages a mutex's lock and unlock operations.

It ensures a mutex is automatically locked when the lock_guard object is initialised

It ensures a mutex is automatically unlocked when the lock_guard object goes out of scope.

Summary: it handles the lock and unlock process for a mutex, preventing them from being forgotten by a programmer.

## Benefits of std::lock_guard

### 1) Thread-safe
std::lock_guard is thread-safe, ensuring only 1 thread can acquire the mutex's lock at a given time.

### 2) Exception-safe
If an exception is thrown during executing the critical section (area which is locked off from other threads) of code, the mutex is still automatically unlocked.

## std::lock_guard() syntax
The mutex object having a lock_guard applied to MUST be initialised before the lock_guard object is initialised.
- The mutex object is an argument for the lock method of the std::lock_guard object.

```c++
#include <mutex>

std::mutex mtx;

void foo(){
	std::lock_guard<std::mutex> lock(mtx);
	//critical section
} //lock_guard goes out of scope, mutex unlocked
```

