[[3 - Continuous vs Discrete Signals]] $\leftarrow$ Back

---
# What is Similarity between Signals
Similarity between signals expresses how equivalent a given signal is to another.

# Measuring Similarity 
Similarity, between two signals, $x[n]$ and $y[n]$, is defined as:
$$
S(x,y) = \sum_{i=0}^{N-1}\bigg[x[i] \cdot y[i]\biggr]
$$
$$
-\infty < S(x,y) < \infty
$$
As...
- $S(x,y) \rightarrow -\infty$, signals are LESS similar.
- $S(x,y) \rightarrow \infty$, signals are MORE similar