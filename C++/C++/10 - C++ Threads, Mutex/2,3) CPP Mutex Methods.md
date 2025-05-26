[[2,2) Setting up a Mutex]] <- Back
[[2,4) Locks and Exceptions]] <- Next

---
## CPP Mutex Methods

### std::mutex::lock()
The lock() method allows for the current thread to lock the section of the code, ensuring only it can access that locked section of code until it releases the lock via the unlock method.

### std::mutex::unlock()
The unlock() method releases the lock the current thread holds, enabling other threads to then acquire the lock and execute the code beyond the lock point.

MUST release the lock otherwise the execution of that section of code will never continue beyond the first lock as the first thread keeps hold of the lock.

### std::mutex::try_lock()
The try_lock() method attempts to lock the mutex and returns a boolean value whether the attempt to lock was successful.
- returns true if mutex locked.
- returns false if mutex wasn't able to be locked (typically because another thread holds the lock).
