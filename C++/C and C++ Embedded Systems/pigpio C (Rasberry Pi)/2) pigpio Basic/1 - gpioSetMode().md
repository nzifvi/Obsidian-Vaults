
---
## What is gpioSetMode()
gpioSetMode() is a function used to set the mode of a GPIO.
- Typically sets to either input or output.

#### gpioSetMode Function 
```c
int gpioSetMode(unsigned gpio, unsigned mode);
```
gpioSetMode() returns an int, indicating the result of the attempt to set a gpio's mode.
- if return = 0, gpio set to the given mode.
- else, if return = PI_BAD_MODE || return = PI_BAD_GPIO then something has gone wrong.

gpio is the gpio to set the mode of.

mode is the mode to set the gpio to.