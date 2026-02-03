[[1,2 - Control System Requirements for Autonomous Mobile Robots]] $\leftarrow$ Next

---
# What are Control Systems?
Control systems enable mobile robots to be completely autonomous.
- In order to be completely autonomous, control system must perform a lot of complex info processing in real time.
- Control systems ALSO operate in environment where boundary conditions change rapidly.

Usual approach to building control systems = decompose problem into a series of functional units.
- Method called functional decomposition.
![[Pasted image 20260201214131.png]]

Another approach to building systems = task achieving decomposition.
- Task achieving behaviours are identified and used to decompose the problem in a similar way to functional decomposition.
- Each slice is implemented and then linked to form the control system.

![[Pasted image 20260201214423.png]]

Task achieving decomposition results in radically different architecture for control systems than other decomposition methods.