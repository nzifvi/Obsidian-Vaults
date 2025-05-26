[[2 - Terminating pigpio]] <- Next

---

## How to setup pigpio in source code

1) Include pigpio library using include pre-processor directive.
	- If including pigpio into c++ source code, use extern "C", as pigpio is a C library

```c++
extern "C" {
	#include <pigpio>
}
```

2) Initialise pigpio library.
	- Do in main, before using ANY library functions.

```c++
extern "C"{
	#include <pigpio>
}

int main(){
	if(gpioInitialise() < 0){
			// handle a failure of pigpio failing to initialise
	}
}
```

#### NOW READY TO USE PIGPIO FOR GPIO.