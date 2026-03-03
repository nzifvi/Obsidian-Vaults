[[6,2 - GA Population Loop Implementation]] $\leftarrow$ Back
[[7,2 - Elitism]] $\leftarrow$ Next

---
# Converging
Convergence is when genotypes of population become stable and stop changing.
- Usually due to fitness not improving between generations as most population members have very similar genotypes.

$$
f(\Omega_{i+1}) \approx f(\Omega_i) 
$$
Two types of convergence exists:
1) Global Convergence
2) Premature Convergence

Making effective GAs requires balancing...
1) Convergence, aka exploitation.
2) Variety, aka exploration
## 1) Global Convergence
Occurs when GA process finds the global maximum.
- Goal of GA.

## 2) Premature Convergence
Population converges on a local maximum too quickly.
- Diversity in genotypes decreases too early.

Premature convergence occurs when...
1) Selection pressure too strong.
	- Different forms of natural selection result in different amounts of selection pressure.
2) Mutation rate is too low.
	- Tuning mutation rate allows for improved genetic diversity.
3) Population size is too small.
	- Increasing population size increases exploration of a population.
4) Elitism.
	- The amount of elitism may be too much.

Various methods exist to prevent premature convergence.