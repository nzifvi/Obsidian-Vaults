[[1,2 - Components of Population Members]] $\leftarrow$ Next

---

# Evolution implementing as Genetic Algorithms
For evolution to occur, a population which the following is required:
1) Has variation.
2) Undergoes selection.
3) Reproduces with heredity.

# Variation in Population
Population is not uniform. 
- Changes in the population occurs randomly at a given chance.
- Mutations can be harmful or beneficial.

Traits in members of the population are beneficial or harmful.
- Harmful means a trait which decreases their fitness score.
- Beneficial means a trait which increases their fitness score.

# Selection in Population
Some members of the population are more fit (a score based on a fitness function).
- The higher the fitness of population member, the more likely they are to reproduce.

Fitter population members being more likely to produce means beneficial mutations are more likely to enter the next population.
- Beneficial mutations result in an increase in fitness score.

# Heredity in Population
New generations are produced by reproduction.
- Let $\Omega_i$ denote the $i^{th}$ generation.

Offspring, part of $\Omega_{i+1}$ (next generation), will be similar to their parents which were part of prior generation.
- Allows for...
1) Traits of their parents which were beneficial (resulted in higher fitness score) to remain.
2) Mutations which are beneficial (resulted in higher fitness score) to remain.











# Variants of GAs as Chromosomes
Chromosomes refer to a candidate solution to a problem.
- Normally encoded as a bit string.

Each locus, index, of the chromosome has 2 possible alleles: 0 or 1.
$$
C<0...n-1>
$$
$$
\forall c, c \in C| c = 1 \lor c = 0
$$
GA processes populations of chromosomes, replacing each population with another.
# Variant Parameters as Genes
Genes are either single bits or short blocks of adjacent bits which encode a particular parameter in a given variant.

All of a variant's parameter values construct it's chromosome bitstring: the combination of values which uniquely identify that variant from the population.
- An Allele in a bit string is either 0 or 1.
- Each gene in a genome is located at a specific locus (index) within the genome.

The combination of chromosome values determines the bitstring.