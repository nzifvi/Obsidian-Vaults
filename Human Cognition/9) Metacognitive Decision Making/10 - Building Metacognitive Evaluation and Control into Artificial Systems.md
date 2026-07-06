[[9 - Metacognition in DNNs & LLMs]] $\leftarrow$ Back

---
# Slow and Fast AI (SOFAI)
SOFAI is a system, still under development, for solving planning problems under time constraints.

SOFAI has 2 solvers:
1) System 1 (S1)
2) System 2 (S2)

System 1 (Fast) is..
- Automatic and intuitive.
- Reliant on heuristics.
- Imprecise.
- Good for solving simpler problems.

System 2 (Slow) is...
- Intentional and effortful.
- An implementation of logical and rational thinking.
- Good for complex decisions.

SOFAI system ALSO contains a metacognitive module (MC) which is used to select the appropriate solver.
- MC is an implementation of metacognitive control.
- Neither solver is better than the other. One is just more appropriate than the other for a given task.
- Role of MC: choose what solver to pick.

# How MC decides to use S1 or S2
The MC uses S1 by default. However, it can choose to re-attempt solving a problem with S2 based on the following considerations.
1) Previous performance of S1.
2) Confidence of S1 (measured in self-consistency)
3) Time/resources available for an S2 solution.
	- S2 requires more time, and potentially resources, to solve a task.
4) Cost/benefit evaluation.
	- Is an S2 solution beneficial given how much it costs to produce?


