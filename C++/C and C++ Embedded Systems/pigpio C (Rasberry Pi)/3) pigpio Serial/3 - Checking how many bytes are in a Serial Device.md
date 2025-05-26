[[2 - Writing and Reading from Serial Devices]] <- Back

---
## How to check how many bytes are available in a Serial Device
serDataAvailable() is a function that, given a valid handle as an argument when it is called, returns the number of bytes ready to be read from the serial device associated with the given handle.

#### serDataAvailable Function
```c
int serDataAvailable(unsigned handle);
```
serDataAvailable takes a single argument: handle.

serDataAvailable returns an integer which...
- Will be the number of bytes available to be read from the serial device, which will be >= 0
- returns PI_BAD_HANDLE if the handle, given as an argument, is not associated with an open serial device.