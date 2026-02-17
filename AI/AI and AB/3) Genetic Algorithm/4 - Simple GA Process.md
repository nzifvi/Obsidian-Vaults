[[3 - GA Operators]] $\leftarrow$ Back

---

# Process of GA
Let...
- $\Omega_ i$ refers to the population at the $i^{th}$ generation.

## Initial Stage
Start with randomly generated population at first gen, $\Omega_1$, such that...
- population has n j-bit chromosomes.
- the alleles in the j-bit chromosomes are randomly generated.

$$
|\Omega_1| = n
$$
## Reproduction Loop
Repeat until n offspring have been created, producing population $\Omega_{i+1}$ from population $\Omega_i$


1) Calculate the fitness score of each chromosome x in the population.
	-  $x\in Omega \Rightarrow f(x)$ denotes the fitness score of chromosome x.

2) Select a pair of parent chromosomes, from current population.
	- Probability of a chromosome being selected increases as fitness score of that chromosome increases.
	- A given chromosome can be selected more than once to become a parent chromosome.

3) Produce 2 identical copies of the parent chromosome for processing before they are added to the new population $\Omega_{i+1}$

4) Determine if the copies should have a crossover operation performed, based on probability $P_{crossover}$
	- If chosen for a crossover, chose a randomly chosen locus, where each locus has an equivalent probability to be chosen, subsequences are then swapped.
	- If not chosen for a crossover, let them remain.

5) Mutate the 2 offpsring chromosome, at each locus, determine whether to mutate the allele based on $p_{mutation}$
	- Has a $p_{mutation}$ probability to mutate.

6) Add to new population $\Omega_{i+1}$

7) If size of new population is odd, randomly remove chromosomes until the size is even.

8) Replace current population with the newly produced population.

9) Go back to step to step 1.

# Details of GA Process
