[[3,1 - MIPS Instruction Set]] <- Back

---
# 1) Arithmetic DM Instructions


## 1.1) ```add```
Used to add two values stored in registers together.

```MIPS ASM
add $a, $b, $c
```
- Adds contents of register b, c.
- Stores result of addition in register a.

## 1.2) ```addi```
Used to add a value in a register and a constant value together.
```MIPS
addi $a, $b, x
```
- Adds contents of register b with value x.
- Stores result of addition in register a.

## 1.3) ```addu```
Used to perform unsigned addition.
```MAPS
addu $a, $b, $c
```
- Adds contents of register b, c.
- Stores result of addition in register a.
## 1.4) ```addiu```
Used to perform unsigned addition between a value in a register and a constant value. Works the same way as ```addi``` with the same format.

## 1.5) ```sub```
Subtracts two values stored in 2 registers and stores it in a given register.
```MAPS
sub $a, $b, $c
```
- Subtracts contents of register c from register b (b - c)
- Stores result of addition in register a (a = b - c).

## 1.6) ```subu```
Subtracts two values stored in 2 registers and gives an unsigned result: storing it in a given register.

## 1.7) ```mult```
Multiplication, done by instruction ```mult```, is done in a special way.

```MAPS
mult $a, $b
```
- Multiplies the values in register a, b together. The result is stored in the hi and lo registers and require the ```mflo```, ```mfhi``` instructions to be read from.

If...
$$
value($t0)\cdot value($t1) < 2^{31}-1
$$
...then the result of multiplication is stored in Lo register.

Else...
part of the result is stored in both Hi and Lo registers.

This is because EACH register is 32 bits (can only represent numbers between 0 and 2^31 - 1).
## 1.8) ```div```
Div works same way as mult...
```MAPS
div $a, $b
```

Except...
- Quotient stored in Lo.
- Remainder stored in Hi.
## 1.9) ```mflo```
Used to move a value stored in Lo register after mult or div instruction performed into a register.

```
mflo $a
```

## 1.10) ```mfhi```
Used to move a value stored in Hi register after mult or div instruction performed into a register.
```MAPS
mfhi $a
```


# 2) Logical Instructions
## 2.1) and
Used to perform bitwise AND between 2 registers and store the result in a given register.
```MAPS
and $a, $b, $c
```
- bitwise ANDs the contents of register b, c.
- Stores result in register c.

```andi``` does the same as and except given a register and a constant value. The result is stored in a given register.
## 2.2) or
Used to perform bitwise OR between 2 registers and store the result in a given register.
```MAPS
or $a, $b, $c
```
- bitwise ORs

## 2.3) xor

## 2.4) nor