[[4 - gpioRead() and gpioWrite()]] <- Back

---
## gpioPWM()
gpioPWM() initiates PWM on the given GPIO.

#### gpioPWM Function
```c
int gpioPWM(unsigned user_gpio, unsigned dutycycle);
```
gpioPWM takes 2 arguments: the gpio to initiate PWM on, and the duty cycle of the PWM.
- duty cycle has a default range of \[0, \255], can be changed using gpioSetPWMrange().

gpioPWM returns an int, indicating the result of the attempt to initiate PWM.
- Returns 0 if successfully began PWM on the given gpio pin.
- Returns PI_BAD_USER_GPIO if given a gpio that was not set to the correct mode, or if it does not exist.
- Returns PI_BAD_DUTYCYCLE if given a duty cycle that is out of bounds for the current range of duty cycle for that gpio.

## gpioGetPWMdutycyle()
gpioGetPWMdutycycle() gets the currently assigned duty cycle of a given gpio.

#### gpioGetPWMdutycycle Function
```c
int gpioGetPWMdutycycle(unsigned user_gpio)
```
gpioGetPWMdutycycle takes 1 argument: the gpio to get the PWM from.

gpioGetPWMdutycycle returns an int, indicating the outcome of the attempt to get the gpio's PWM.
- Returns 0 if off.
- Returns the range if fully on.
- Returns PI_BAD_USER_GPIO if given a non-existing gpio, or if the gpio was not set to the correct mode.
- Returns PI_NOT_PWM_GPIO if the given GPIO was not designated for PWM.
