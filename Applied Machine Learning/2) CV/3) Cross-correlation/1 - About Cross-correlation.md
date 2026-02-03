

---
# What is Cross-correlation?
Cross-correlation calculates how similar two signals, or patterns, are to each other.
- Cross-correlation is a function related to convolution yet different from it. 
- Cross-correlation calculates similarity whilst convolution applies local linear functions.

Correlation is defined as...
$$
O(x,y) = M\cdot I(x,y) 
$$
...where...
$$
M\cdot I(x,y)=\sum_{i=0}^{N-1}\sum_{j=0}^{N-1}\biggr[M(i, j)I(x+i, y+j)\biggr]
$$