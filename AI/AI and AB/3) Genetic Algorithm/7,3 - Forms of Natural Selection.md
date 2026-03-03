[[7,2 - Elitism]] $\leftarrow$ Back
[[7,4 - Selection Pipeline and Details]] $\leftarrow$ Next

---
# Forms of Natural Selection
Natural selection is the mechanism which controls which individuals are SELECTED to reproduce.
- Most methods result in fitter individuals being more likely to be chosen. Weaker ones might still be chosen though.

Multiple methods to naturally select a population of a given generation exist.
- Trade-offs exist between each method.
- Some methods can potentially be combined and experimented with.

Natural selection is what determines the selection pressure of a GA.
- Some forms cause more selection pressure than others.

Some methods are:
1) Truncation Selection
2) Fitness Proportionate Selection
3) Roulette Wheel Selection
4) Rank Selection
5) Tournament Selection
... others exist

# 1) Truncation Selection
Truncation selection is when a subset, containing $\tau$% of the fittest individuals, are only allowed to reproduce.
- Population is sorted by fitness (descending order).
- Only top $\tau$% of fittest individuals in current population allowed to become parents
- All others discarded
- $\tau$ is the percentage of individuals allowed to become parents per generation.
$$
|\Omega_{parents}| = floor(|\Omega_i|\cdot \tau)
$$
To get probability a parent, from the parent subpopulation, is selected. Do...
- Let $v$ denote a candidate parent.
- Let $v\in \Omega_{parents}$

$$
P(v=selected) = \frac{1}{f(\Omega_{parents})}
$$
- Choice is uniform


Truncation selection causes high selection pressure.
- Can cause premature convergence, as genetic diversity decreases rapidly.
- Population size also decreases per generation.
# 2) Fitness Proportionate Selection
Suppose...
$$
\Omega_i= \begin{bmatrix}
g_{1,1}&...&g_{1,n}\\
...\\
g_{|\Omega|,1}&...&g_{|\Omega|,n}
\end{bmatrix}
$$
$$
\vec{f}(\Omega_i)=
\begin{bmatrix}
f(G_1)\\
...\\
f(G_{|\Omega_i|})
\end{bmatrix}
$$
The probability of a population member, v, being selected is equal to...
$$
P(v=selected)=\frac{f(G_v)}{f(\Omega_i)}
$$
# 3) Roulette Wheel Selection

Let S denote the total sum of genotype fitness in a generation.

Let...
$$
\exists r,r \in [0,S]
$$
```pseudocode
procedure: rouletteWheelSelect(Pop, r)
inputs: Population Pop[0,...,n-1], threshold r which determines when to stop the roulette wheel.
Outputs: genotype G

fitnessSum <- 0
i <- 0
while (fitnessSum <= r) do:
	fitnessSum <- fitnessSum + fitness(Pop[i])
	i <- i + 1
return Pop[i]
```

# 4) Rank Selection
Rank selection discards selection by fitness. Instead using selection by rank of fitness.
- Population is sorted in ascending order by their fitness scores.

![[Pasted image 20260220102411.png]]

$$
f(G_{i+1}) \geq f(G_i)
$$
Let $Rank(G_i)$ denote the index of population member $G_i$

Rank selection, rather than using the freq. probability of a fitness score, uses...
$$
P(v=selected)=\frac{Rank(v)}{\sum_{j=1}^{|\Omega_i|}\biggr[j\biggr]}=\frac{2Rank(v)}{|\Omega_i|(|\Omega_i|+1)}
$$
Rank selection results in...
- $G_{i+1}$ only being slightly better than $G_i$
- Controlled and stable selection pressure: more stable exploration.
- Preventing outliers from dominating, due to massive fitness scores.
- All individuals in a population have a chance for reproduction: increased genetic diversity.


# 5) Tournament Selection
Tournament selection is a type of natural selection used in tandem with crossover ([[8 - Sexual Recombination]]).

![[Pasted image 20260220105115.png]]

Pick 2 population members ($A_1, A_2$), at random, and evaluate them
- Let the fitter one be a parent.
$$
A_{parent}=argmax\biggr(f(A_1), f(A_2)\biggr)
$$
Pick another 2 population members ($B_1, B_2$), at random, and evaluate them.
- Let the fitter one be the other parent.
$$
B_{parent}=argmax\biggr(f(B_1), f(B_2)\biggr)
$$
Then cross them over to produce the child.
- Add child to new population
$$
\Omega_{i+1} = \Omega_{i+1} + \{Crossover(A_{parent}, B_{parent})\}
$$
