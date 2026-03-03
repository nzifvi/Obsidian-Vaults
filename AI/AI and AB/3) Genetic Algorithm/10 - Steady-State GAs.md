[[9 - Mutation Rate]] $\leftarrow$ Back
[[11 - Microbial GAs]] $\leftarrow$ Next

---
# What are Steady-State GAs (SSGAs)
SSGAs are an alternative to generational GAs.
- Instead of replacing an entire population to produce the next generation, only some are replaced in the next generation.

![[Pasted image 20260220115656.png]]

```pseudocode
pop <- StaticArray.BUILD()
popFitness <- StaticArray.BUILD()
replacementAmount <- some int <= size of pop

while(GA process not finished) do:
	newPop <- StaticArray.BUILD()
	popFitness <- fitness(pop)
	for i <- 0 to replacementAmount do:
		// perform natural selection.
		// do crossover
		// replace parents with child
		// add to next gen (newPop)
		
	pop <- newPop
```