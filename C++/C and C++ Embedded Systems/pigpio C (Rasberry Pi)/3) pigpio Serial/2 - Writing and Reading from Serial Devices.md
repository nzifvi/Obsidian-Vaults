[[1 - Opening and Closing Serial -  serOpen() & serClose()]] <- Back
[[1 - Opening and Closing Serial -  serOpen() & serClose()]] <- Next

---
## Writing to Serial Devices
To write a byte to the serial bus, after it has been opened, use serWriteByte()

#### serWriteByte Function
```c
int serWriteByte(unsigned handle, unsigned bVal);
```
serWriteByte function takes 2 arguments: handle and bVal.
- handle is the handle of the serial device.
- bVal is the byte to write to the serial device.

serWriteByte function returns an int value, indicating the result of the attempt to write to the serial device.
- Returns 0 if attempt to write to the serial device was successful.
- Returns PI_BAD_HANDLE if the given handle was not a handle which refers to an open serial device.
- Returns PI_BAD_PARAM if the value of bVal was not a byte.
- Returns PI_SER_WRITE_FAILED if the attempt to write to the serial device failed.

## Reading from Serial Devices
To read a byte from a serial device, after it has been opened, use the serReadByte() function.

#### serReadByte Function
```c
int serReadByte(unsigned handle);
```
The serReadByte function takes a single argument: handle.
- handle is the handle of the serial device to read from.

serReadByte function returns an int value, which can be multiple possible values.
- If the serReadByte was successful in reading from the serial device, it returns the read byte which is >= 0.
- If the handle attempted to reference a non-opened serial device, returns PI_BAD_HANDLE.
- If there is no data ready to be read from the serial device, returns PI_SER_READ_NO_DATA.
- Else, if the attempt to read the byte failed, returns PI_SER_READ_FAILED.