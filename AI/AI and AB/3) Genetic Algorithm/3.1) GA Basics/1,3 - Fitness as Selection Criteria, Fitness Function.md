[[1,2 - Components of Population Members]] $\leftarrow$ Back
[[2 - Search Spaces and Fitness Landscapes]] $\leftarrow$ Next

---
# Selection Criteria: Fitness
Fitness is what drives evolution: aiming to increase the overall fitness of the next generation.
- Let $f$ be a fitness function

Natural selection aims to achieve...
$$
f\biggr(\Omega_{i+1}\biggr) \geq f\biggr(\Omega_i\biggr)
$$
- fitness of next generation is greater than or at least equal to current generation.


Members of a population with a higher fitness score are more likely to be chosen to reproduce.
- $v \in \Omega_1$
- $f(v) \rightarrow \infty$, $p(v)$ = chosen for reproduction $\rightarrow \infty$

Probability a population member, $i$, reproduces is equal to...
$$
P(i)=\frac{f(v)}{f(\Omega_i)}
$$

# Fitness Functions
A fitness function, $f$, is a mathematical function which...
- Takes a genotype, $G$, OR measurements as input
- Returns a fitness score corresponding to $G$ OR measurements.

Fitness function's expression depends on what is trying to be optimised.
- If trying to optimise jump height, a function which takes a set of measurements (height jumped) would be required.

## Examples
Suppose a car drives around a race track
- $\frac{\Delta||\vec{v||}}{\Delta t}$ is the average speed from the start till the last valid position (finish line OR time before going off track)
- $m$ is the total distance travelled.

Let fitness function f, be equal to...
$$
f\biggr(\frac{\Delta ||\vec{v}||}{\Delta t}, m\biggr)=1.5\frac{\Delta||\vec{v}||}{\Delta t}+1.5 m
$$
Suppose we are trying to fit n items into a bag of $max_{volume}$
- Each item, i, has $volume_{i}$
- Each item, i, has $value_i$ 

Let the fitness function, f, be equal to...

$$
x = \sum_{i=1}^n\biggr[value_{i}\biggr]
$$
$$
y=\sum_{i=1}^n\biggr[volume_i\biggr]
$$
$$
f(x, y, max_{volume})= \begin{cases}x > max_{volume} \Rightarrow f(x,y)=0\\ x < max_{volume} \Rightarrow f(x,y) = y \end{cases}
$$
