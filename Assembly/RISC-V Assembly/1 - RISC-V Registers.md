
---
# RISC-V Registers

RISC-V provides 32 integer registers.
- Each register occupies 32 bits.

Register x0: hard-wired to value 0.
- Used to discard contents of another register by nulling it.
- Used as a source of constant 0

Registers x1-x31: general purpose registers that can be used as…
- Boolean flags.
- Signed or unsigned integers.
- Pointer values (stack and frame pointers)

Program counter register (PC):
- Points to instruction to be executed next.
- Cannot directly be written to / read from.
- Only affected by side-effects of some instructions.

# RISC-V Usage Conventions
