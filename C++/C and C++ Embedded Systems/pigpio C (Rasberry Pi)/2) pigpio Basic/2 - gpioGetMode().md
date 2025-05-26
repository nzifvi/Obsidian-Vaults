[[1 - gpioSetMode()]] <- Back
[[3 - GPIO pin modes]] <- Next

---
## What is gpioGetMode()
gpioGetMode() is a function that gets a given gpio's current mode.

#### gpioGetMode Function
```c
int gpioGetMode(unsigned gpio);
```
returns an integer value which is the gpio mode of the given gpio pin.

gpio is the gpio pin to get the mode of