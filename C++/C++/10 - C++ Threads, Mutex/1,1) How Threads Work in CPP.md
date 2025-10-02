[[1,2) Setting up a Thread]] <- Next

---
## How Threads Work in CPP
Each thread is assigned a function OR method from a class. Upon being assigned a function, or method, that thread will begin executing that function in parallel with other threads.

To use threads, thread header must be included:
```c++
#include <thread>
```

All threads execute in parallel with main. Whilst main executes, a thread will execute until it reaches it's finishes executing.

NOTE: once the calling thread terminates, all threads called from that thread are killed UNLESS they are daemon threads.
- Daemon threads ONLY are killed when main() finishes execution (i.e. if return is executed in main)