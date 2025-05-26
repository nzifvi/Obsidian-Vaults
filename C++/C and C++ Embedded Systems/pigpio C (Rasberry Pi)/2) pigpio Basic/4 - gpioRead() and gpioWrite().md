[[3 - GPIO pin modes]] <- Back
[[5 - gpio Pulse Width Modification]] <- Next

---
## What is gpioRead()
gpioRead() is a function used to read a given voltage, as an integer representation, from a gpio.

#### gpioRead Function
```c
int gpioRead(unsigned gpio);
```
returns an integer, which can equal 1 of 2 things.
1) If the read was successful, returns an integer representation of the voltage.
2) If the read was unsuccessful, returns PI_BAD_GPIO.


## What is gpioWrite()
gpioWrite() is a function used to set a voltage from a gpio.

#### gpioWrite Function
```c
int gpioWrite(unsigned gpio, unsigned level);
```
returns an integer value.
- Returns 0 if write was successful.
- Returns PI_BAD_GPIO if something wrong with the gpio.
- Returns PI_BAD_LEVEL if the given level is out of bounds.

level is the level to set (HIGH OR LOW).
- level = 1 results in 5v being provided to the given gpio.
- level = 0 results in no voltage being provided to the given gpio.