[[5 - Evolution as Search]] $\leftarrow$ Back
[[6,2 - GA Population Loop Implementation]] $\leftarrow$ Next

---
# What are Population GAs?

# Benefits of Population GAs?
Population GAs can have MULTIPLE population members per generation.
- Allows for faster, more efficient searching of a search space.

Can compare between multiple local maximas to find the best maxima out of the ones that have been found.
- In fitness landscape, multiple local maximas may exist.
- Multiple population members can find different local maximas and the best amongst them can be chosen.

# Choosing Initial Gen. Population Size
Choosing 1st generation population size is important.
- Must not be too small otherwise you have a much smaller chance of having a genotype near a local maxima.
- More population members the better.

# Converging
Convergence is when genotypes of population become stable and stop changing.
- Usually due to fitness not improving between generations as most population members have very similar genotypes.

$$
f(\Omega_{i+1}) \approx f(\Omega_i) 
$$

Two types of convergence exists:
1) Global Convergence
2) Premature Convergence

## 1) Global Convergence
Occurs when GA process finds the global maximum.
- Goal of GA.

## 2) Premature Convergence
Population converges on a local maximum too quickly.
- Diversity in genotypes decreases too early.

Premature convergence occurs when...
1) Selection pressure too strong.
2) Mutation rate is too low.
3) Population size is too small.

Various methods exist to prevent premature convergence.