
---
# 1) MIPs Program Segments
MIPs programs require a specific structure to tell assembler where to put data and where to put instructions

```MIPs
.data

.text

.globl main
```

```.data``` is where variables, strings, and other storage space is declared that a MIPs program will use.

```.text``` is where all of the executable instructions will be written.
- Actual source code is written here.

```.globl main``` declares a label, main in this case, which is the entry point for the program's execution.
- Starting function is declared here.