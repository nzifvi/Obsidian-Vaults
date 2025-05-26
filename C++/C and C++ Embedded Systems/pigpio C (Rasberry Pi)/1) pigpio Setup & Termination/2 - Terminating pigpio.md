[[1 - Setting up pigpio]] <- Back

---
## Terminating pigpio
gpioTerminate() is used to terminate the pigpio library. It has no return.
- Call before the program exits.

gpioTerminate() resets DMA channels, deallocates heap memory, and terminates any gpio threads launched using pigpio.