[[2 - Writing and Reading from Serial Devices]] <- Next

---
## Opening: serOpen()
serOpen() function is used to open a serial device, at a baud rate given as an argument, plus flags also given as an argument.

#### serOpen Function
```c
int serOpen(char *sertty, unsigned baud, unsigned serFlags);
```
char \*sertty is an array of characters (string) which is the device to open as a serial device.
- Device name MUST start with either...
	1) /dev/tty
	2) /dev/serial

baud is the baud rate to open the serial device with.

let serFlags = 0 as there are no flags currently defined.

serOpen() function returns...
- A handle >= 0 if the serial device could be opened successfuly.
	- This handle is how the serial device MUST be referred to in source code.
- PI_NO_HANDLE if the serial device could not be located via the \*sertty string.
- PI_SER_OPEN_FAILED if the serial device specified was unable to be opened.
## Closing: serClose()
Once a serial device is no longer required to communicate with another device, it should be closed. The serClose() function is what does that.
- Any class simulating a serial device should have serClose() in it's destructor at a minimum.

#### serClose Function
```c
int serClose(unsigned handle)
```
serClose() function takes a singular argument which is the handle of the serial device.

serClose() returns an integer value, indicating the outcome of the attempt to close a serial device.
- returns 0 if closing of serial device was successful.
- returns PI_BAD_HANDLE if the given handle did not refer a serial device that was opened previously.
