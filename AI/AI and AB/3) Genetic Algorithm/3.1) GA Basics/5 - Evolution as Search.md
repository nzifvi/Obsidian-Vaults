
---
# Search Spaces
The number of genes in a genotype, and the number of alleles a gene can express, form a search space.

A search space is a ${n+1}^{th}$ dimensional space containing all possible combinations of alleles a genotype can be.
- Each gene has it's own dimension.
- A genotype of $n$ length results in an $n^{th}$ dimensional search space.
- One dimension is the fitness function

Let G represent a genotype
Suppose...
$$
|G| = 4
$$
Let g represent a gene in the genotype G.
$$
\forall g, g\in G | g\in \mathbb{N} \wedge 1 \leq g \leq 90
$$

The number of possible combinations of genes, in the search space of G, is...
$$
90^5 
$$
- $90^5$ possible combinations of genes.

# Evolution as Searching the Search Space
Evolution's goal is to achieve the most optimal combination of genes for a given problem.
- A genotype with a maximum fitness score, compared to other genotypes, is the goal of evolution.
$$
S = \{G_1,...G_n\}
$$
$$
G_{optimal}=max(S) | \forall G, G\in S \Rightarrow f\biggr(G_{optimal}\biggr) \geq f\biggr(G\biggr)
$$
## Searching Organised Search Spaces
Organised search spaces are easier to search than unorganised ones.