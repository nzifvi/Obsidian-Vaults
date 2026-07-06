

---
# What is Cross-correlation?
Cross-correlation calculates how similar two signals, or patterns, are to each other.
- Cross-correlation is a function related to convolution yet different from it. 

Cross-correlation differs from convolutions.
- Cross-correlation used to detect similarity in two signals or patterns.
- Convolutions used to apply local, linear functions.

Cross-correlation is defined as...
$$
O(x,y) = M\cdot I(x,y) 
$$
...where...
$$
M\cdot I(x,y)=\sum_{i=0}^{N-1}\sum_{j=0}^{N-1}\biggr[M(i, j)I(x+i, y+j)\biggr]
$$

# Properties of Convolutions & Cross-Correlations
1) Convolutions and Correlations are translation equivariant.
	- If an image is translated, and then convolved/cross-correlated, it would produce the same output if convolving/cross-correlated the same image without the translation.
	- This is because convolutions and cross-correlations ONLY consider local neighbourhoods.

2) Convolutions & cross-correlations are not equivariant to general geometric transformations, besides translations.
	- This is because the relationship between pixels, in a local neighbourhood, becomes distorted.

