[[7,1 - Convergence]] $\leftarrow$ Back
[[7,3 - Forms of Natural Selection]] $\leftarrow$ Next

---
# What is Elitism?
Elitism is a process, used when creating the next generation, where k of the fittest individuals from current generation are directly copied and placed into the next generation.
- Ensures that the fittest k genotypes from current generation are not lost.

Elitism is a type of selection but is NOT natural selection.
- Elitist selection selects, and preserves, the fittest k individuals.
- Elitist selection should be used in tandem with natural selection.

Elitism very quickly causes convergence as it causes HIGH selection pressure
- Will most likely cause premature convergence due to rapidly decreasing genetic diversity.
- Entire population will quickly converge to where the fittest members are in the fitness landscape.

Elitism can be useful when it is used.
- When k is small, elitism can work.
# How to perform Elitist Selection
Given a generation $\Omega_i$

1) Sort $\Omega_i$ by fitness in descending order.

$$
sort(\Omega_i)=\begin{bmatrix}G_1\\...\\G_{|\Omega_i|}\end{bmatrix} | f(G_j) \geq f(G_{j+1})
$$
2) The k fittest individuals are then added to the new generation
	- No mutation.
	- No reproduction (that is done later)
	- Just added WITHOUT change.


