[[8 - Sexual Recombination]] $\leftarrow$ Back
[[10 - Steady-State GAs]] $\leftarrow$ Next

---
# Importance of Mutation Rate
Each gene of a child has a uniform probability to mutate.
- Mutation promotes genetic diversity which in turn promotes exploration.


If...
- Mutation rate too low: evolution becomes too slow and the evolution process can get stuck on a local maxima.
- Mutation rate being too high can cause a population being pushed out of good areas of fitness landscape.

Mutation rate must be just right.

# Choosing Mutation Rate
No definite answer. Rule of thumbs exist but they may not work as well.
- Best to tinker with mutation rates.

Let $p_{mutation}$ denote the probability of a gene mutating.

Two rules of thumbs exist:
1) $0.01 \leq p_mutation \leq 0.05$
2) $p_{mutation} \approx \frac{1}{|G|}$
