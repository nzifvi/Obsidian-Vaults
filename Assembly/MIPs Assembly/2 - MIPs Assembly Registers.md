
---
MIPs assembly has 32 general purpose 32 bit registers.
- Some of these registers have a special purpose though.

The registers can be broken into separate groups based on how they are used...

# 1) Reserved Registers
Reserved registers are registers which have a special purpose and are typically used by a process.
- Reserved registers should rarely be 

| Reg. Name  | Reg. Number | What it does                                            | Preserve on Call? |
| ---------- | ----------- | ------------------------------------------------------- | ----------------- |
| $at        | $1          | Used by assembler to translate complex instructions     | N/A               |
| \$k0, \$k1 | \$26, \$27  | Used by operating system kernel and interrupt handlers. | N/A               |
# 2) Temporary Registers
| Reg. Name   | Reg. Number | What it does                        | Preserve on Call?                                     |
| ----------- | ----------- | ----------------------------------- | ----------------------------------------------------- |
| \$t0 - \$t7 | \$8 - \$15  | Used for intermediate calculations. | No. Temporary register's values must be caller-saved. |
| \$t8, \$t9  | \$24, $25   | Used for intermediate calculations. | No. Temporary register's values must be caller-saved. |

## 2.1) Caller-saved Registers
Caller-saved registers mean that the calling function, aka caller, must be the thing that saves any values in a temporary registers that it needs to BEFORE the calling function is called.

# 3) Saved Registers

| Reg. Name   | Reg. Number | What it does                                                                                           | Preserve on Call?           |
| ----------- | ----------- | ------------------------------------------------------------------------------------------------------ | --------------------------- |
| \$s0 - \$s7 | \$16 - \$s3 | Used for program variables which must continue to save their values between and during function calls. | Yes. These are callee-saved |

# 4) Function Result and Argument Registers
| Reg. Name | Reg. Number | What it does                                                                                      | Preserve on Call?            |
| --------- | ----------- | ------------------------------------------------------------------------------------------------- | ---------------------------- |
| $v0, $v1  | $2, $3      | Stores return values of functions. Also used to hold system call code before executing a syscall. | No, value is being returned. |
| $t0 - $t7 | $4 - $7     | Function arguments. Used to store values being passed to a function.                              | No.                          |

# 5) Pointer Registers
| Reg. Name | Reg. Number | What it does                                                                                                                                                 | Preserve on Call?            |
| --------- | ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------- |
| $gp       | $28         | Global Pointer:<br><br>Used by compiler to access statically allocated global data efficiently.                                                              | Yes. These are callee-saved. |
| $sp       | $29         | Stack Pointer:<br><br>Points to the top (lowest address) of stack. Required for local memory and function calls.                                             | Yes. These are callee-saved. |
| $fp       | $30         | Frame Pointer:<br>Used to point to the base of the current function's stack frame (optional, often unused)                                                   | Yes. There are callee-saved. |
| $ra       | $31         | Return Address:<br><br>Holds memory address of the instruction immediately following a jal (jump and link) instruction. Also used to return from a function. | Yes. There are callee-saved. |

