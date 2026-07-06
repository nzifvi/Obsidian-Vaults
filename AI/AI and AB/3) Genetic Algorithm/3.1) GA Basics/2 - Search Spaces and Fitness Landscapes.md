[[1,1 - Evolution and Evolutionary Requirements]] $\leftarrow$ Back
[[3 - GA Operators]] $\leftarrow$ Next

---
# Search Spaces
A search space refers to a collection, or set, of possible candidate solutions to a given problem.

Algorithms which search the search space is a method used to choose which candidate solutions to test at each search stage.
- Normally, next candidate solutions to be tested depend on results of previous searches.
- Most algorithms assume the less the distance between candidate solutions, the higher quality they may be.

## Distance between Candidate Solutions
The distance between candidate solutions is the amount of different alleles in their genome bitstring.
- How many parameters are different between 2 variants.

![[Pasted image 20260206150803.png]]

6 alleles are different. Therefore the distance between the above genomes is 6.


# Fitness Landscapes
A fitness landscape is a plot of the search space, holding all possible candidate solutions, alongside the fitness scores of said candidate solutions.

Consider...
- A genome (bitstring) of length N
$$
A[0...n-1] | len(A)=N
$$
A fitness landscape is a N-dimensional plot where EACH possible candidate solution is a point in N-dimensions.

In the fitness landscape, there are local and absolute maximas and minimas.
- Evolution causes populations to move along fitness landscapes, approaching local maximas.
- Local maximas correspond to an optimal solution.