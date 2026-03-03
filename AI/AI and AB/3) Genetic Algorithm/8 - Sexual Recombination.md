[[7,4 - Selection Pipeline and Details]] $\leftarrow$ Back
[[9 - Mutation Rate]] $\leftarrow$ Next

---
# What is Sexual Recombination?
Recombination = process, occurring in nature, where genes of parents are recombined mixed.
- Not all genes come from one or the other parent. Child gets a mixture of their genes.

- Let $P$ denote a parent.
- Let $C$ denote a child

$$
Parents(C_i)= \{P_j, P_k\}
$$
$$
Pj \in \Omega_i \wedge Pk \in \Omega_i
$$
$$
C_i \in \Omega_{i+1}
$$
$$
P_1 = <a_1,...,a_10>
$$
$$
P_2 = <b_1,...,b_{10}>
$$
![[Pasted image 20260220103710.png]]

Sexual recombination AKA crossover.
# Benefits of Sexual Recombination
Schema theorem states:  GAs evaluate combinations of genes in parallel.
- Multiple population members explore search space.
- The population shares information about the fitness landscape.

Suppose...
- $P_1$ has a bad allele for gene $a_1$ but a good gene for $a_2$.
- $P_2$ has a good allele for gene $a_1$ but a bad gene for $a_2$
- $P_1$ and $P_2$ can have a child which has BOTH a good gene $a_1$, $a_2$

This is achieved via sexual recombination.