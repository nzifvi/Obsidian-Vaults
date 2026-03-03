[[1 - Stochastic Optimisation]] $\leftarrow$ Back

---
# What is Simulated Annealing?
Simulated Annealing is a type of stochastic optimisation method.

Inspired by process of physical annealing where material is heated and slowly cooled: forming a uniform structure.
- Material is heated to a sufficiently high temp: ensuring a random state.
- Cooling process is performed slowly to ensure thermal equilibrium.
- Atoms place themselves in a pattern corresponding to global energy minimum: an optimal configuration.
- If metal cooled too quickly, atom configuration is suboptimal.

# How Physical Annealing works
Laws of thermodynamics: at temperature, $t$, the probability of an increase of energy, in magnitude of $\Delta E$, is given by...

$$
P(\Delta E)=e^{-\frac{\Delta E}{kt}}
$$
- k is the Boltzmann's constant
![[Pasted image 20260226122427.png]]

$P(\Delta E)$ decreases as $\Delta E$ increases.
- Probability of change to a higher energy state decreases as size of energy jump increases.
- Higher temp. makes larger energy changes more likely.

# Physical Annealing to Simulated Annealing
Simulated Annealing uses same process as physical annealing to optimise.
- Instead of energy, simulated annealing uses fitness.
- temp is still used.

$\Delta F$ denotes the magnitude of fitness increase.
$$
\Delta F = F_{new}-F_{old}
$$
$P(\Delta F)$ denotes the probability of an increase in fitness of magnitude $\Delta F$
$$
P(\Delta F) = e^{-\frac{\Delta F}{t}}
$$
The idea of simulated annealing is...
- Let $r\in [0, 1]$

$\Delta F > 0 \Rightarrow$ accept new state 
$\Delta F \leq 0 \Rightarrow$ accept new state with probability $P(\Delta F)$
- $P(\Delta F) > r \Rightarrow$ accept
- $P(\Delta F) \leq r \Rightarrow$ deny

## Simulated Annealing Process

1) Change (mutate) genotype by a random amount.
	- Small changes being more probable.

2) Measure the difference in fitness between old and now changed genotype.
$$
\Delta F = F_{new}-F_{old}
$$
3) If $\Delta F > 0$, accept new mutated genotype solution.
	- Else, accept with probability $P(\Delta F)$

4) Reduce temperature by small, defined amount:
	- Other methods exist: can do logarithmic decrease, linear decrease, etc.
	- [[2,2 - Simulated Annealing Temperature Scheduling]] $\leftarrow$ covered in
$$
t' = t-\Delta t
$$
5) Go to 1 until satisfied.