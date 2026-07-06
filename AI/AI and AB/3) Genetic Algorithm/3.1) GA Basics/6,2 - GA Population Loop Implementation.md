[[6,1 - Population GAs]] $\leftarrow$ Back
[[7,1 - Convergence]] $\leftarrow$ Next

---
# Pseudocode

```
// Initialise P individuals as population
pop <- StaticArray_BUILD()
popFitnesses <- StaticArray_BUILD()
// ||Pop|| = ||Fitness||, as each pop has their fitness stored in
// corresponding indices.
lastGenFitness <- 0
 
while (!satisfied or no further improvement in generations or maxGen hit) do:
	// evaluate fitness of current gen
	for i <- 0 to n do:
		popFitnesses[i] <- fitness(pop[i])
		
	// create population for new generation
	pop2 <- StaticArray_BUILD()
	
	// select population members, based on fitness:
	//    - frequency probability of their fitness
	genFitness <- GenerationFitness(pop)
	randThreshold <- randomDouble(0.0, genFitness)
	for i <- 0 to n do:
		if fitness(pop[i]) / (genFitness - fitness(pop[i])) <= randThreshold:
			pop2.add(
				mutate(pop[i])
			)
	pop <- pop2

// once GA loop ends, best individual in final generation is the solution
return bestIndividual in pop
```

```pseudocode
Procedure: GenerationFitness()
Inputs: Generation G[0,...n-1] of n population.
Outputs: Mean fitness of Generation G

sum <- 0
for i <- 0 to n do:
	sum <- sum + fitness(G[i])
return sum / n
```

# Loop Conditions

## Until Satisfied
Current generation has hit a target fitness:
$$
\exists target_f
$$
$fitness(\Omega_i) = target_f \Rightarrow$ terminate loop
- Should have some tolerance applied, unlikely you will exactly hit $target_f$

## No Further Improvement
Until the difference in fitness between generations begins to approach 0.
$$
\Delta f = f(\Omega_{i+1})-f(\Omega_i)
$$
As $\Delta f \rightarrow 0$, amount improvement in next generation decreases.
- Good point to terminate potentially.
- OR it may have got stuck in a local maxima.

## maxGen Hit
maxGen is a number which denotes a point for the GA loop to stop at.
- Could potentially go on forever without a set stopping point.

# Data Structures for GA Implementation
## Genotype 
Stored as a row vector
$$
G_1 = \begin{bmatrix}g_1&...&g_{n}\end{bmatrix}
$$
## Population of $i^{th}$ Generation
Stored as a 2d matrix where each row is a genotype (member of population).
- No of columns = length of genotypes (MUST BE EQUIVALENT LENGTH FOR ALL GENOTYPES)
- No of rows = size of population
$$
\Omega_i = \begin{bmatrix}
g_{1,1}&...&g_{1,n}
\\
...
\\
g_{|\Omega,1|}&...&g_{|\Omega|,n}
\end{bmatrix}
$$
## Fitness of $i^{th}$ Generation
Stored as a 1d vector.
- Each row is fitness of a given genotype.
$$
\vec{f}(\Omega_i) = \begin{bmatrix}
f(G_1)
\\
...
\\
f(G_{|\Omega]})
\end{bmatrix}
$$

# 1st Generation
Best way to implement first generation is to randomise genes of all genotypes with each allele having a uniform probability to occur.

Let A denote the alleles
$$
A=\{1,2,3,4\}
$$
$$
\forall a, a\in A | P(A=a)=\frac{1}{|A|}
$$
