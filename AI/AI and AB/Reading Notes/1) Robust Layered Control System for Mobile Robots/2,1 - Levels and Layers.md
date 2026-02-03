[[1,3 - Starting Assumptions]] $\leftarrow$ Back
[[2,2 - Control Layers, Subsumption Architecture]] $\leftarrow$ Next

---

Multiple methods to building intelligent, autonomous robot control systems exist.
- All start with decomposing problem into pieces, solving subproblems of each piece, then composing solutions.
- Task Achieving Decomposition, TAD, handles this process differently.

TAD breaks the problem down into a series of desired behaviours, or results, of each level.
- These levels referred to as levels of competence

A level of competence, LOC, specifies a desired set of behaviours, for a control system, over any environment the robot may encounter.
- The higher the LOC, the more specific and specialised the set of behaviours will be.
![[Pasted image 20260201220940.png]]
- $L_0$ will be a more general set of behaviours than $L_1$

