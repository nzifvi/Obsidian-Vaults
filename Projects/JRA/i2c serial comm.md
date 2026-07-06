
---
# What is i2c

i2c enables one or more controller devices to communicate with all worker devices.
- Controllers cannot communicate with each other.
- Workers can communicate to controllers. Controllers to workers.

i2c devices can communicate at 100kHz or 400kHz.

i2c has overhead. For every 8 bits of data transmitted, one extra bit of meta data must also be transmitted.
- Extra meta data bit is the "ACK/NACK" bit.

# i2c Signals
Each i2c bus consists of 2 signals: SDA and SCL.
- Serial data (SDA) is the data signal.
- Serial clock (SCL) is the serial clock signal.

# i2c Message Protocol
## Basics
i2c messages are broken up into 2 types of frame: address frame and data frames.
- Address frames indicate which worker.
- Data frame is >= 1 8-bit data packet passed from controller to worker or worker to controller.

Data placed on SDA line after SCL goes low.

To read data on SDA once set, SCL goes high.

## Start Condition
To initiate the address frame, controller sets SCL high and pulls SDL low.
- Indicates to all workers that a transmission is beginning.

## Address Frame
Address frame is the very first frame in any new communication sequence.
![[Pasted image 20260609181552.png]]

Address frame consists of 9 bits.
- First bit indicates if this is a read (1) or write (0) operation.
- 7 bits are the address of the worker.
- Last bit is the ACK/NACK bit.
	- ALL frames (both address and data) will have their last bit be the ACK/NACK bit.

Once first 8 bits of address frame are sent, the receiving worker device is given control over SDA.
- Receiving device must pull SDA line to low before 9th clock pulse.
- If receiving device does not pull SDA line to low before 9th clock pulse, it can be assumed receiving device did not receive data or was unable to parse message.

## Data Frames

## Stop Condition
