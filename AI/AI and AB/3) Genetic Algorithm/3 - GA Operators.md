[[2 - Search Spaces and Fitness Landscapes]] $\leftarrow$ Back
[[4 - Simple GA Process]] $\leftarrow$ Next

---
# 3) GA Operators

## Selection
Selection operator selects chromosomes from the population for reproduction.
- Higher the fitness score of a chromosome, more probable that chromosome is chosen for reproduction.
## Crossover
Crossover operator randomly selects a locus in a chromosome's bitstring and exchanges a subsequence of the bitstring with another subsequence from another chromosome.
- Process produces 2 offspring genomes from 2 parent genomes.

Crossover operator approximately replicates biological replicated between 2 single-chromosome organisms.

## Mutation 
Mutation operator randomly flips some of the bits in a chromosome bitstring.
- Mutation can occur at each and every position in a bitstring based on a probability.
- $P(A[i]$ $is$ $mutated$) = 0.001 (or some other small probability)