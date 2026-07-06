[[4,3 - PoS Tagging]] $\leftarrow$ Back
[[4,4,2 - Hidden Markov Models]] $\leftarrow$ Next

---
# PoS Tag Sequences
A tag sequence is a sequence of tags derived from a string.
- Each element was the most likely tag assigned to a word.

Tag sequences can be used to increase PoS tagging accuracy.
- Implemented using a Hidden Markov Model (HMM)

Let $\vec{s}$ denote a string
$$
\vec{s}_{n\times1} = \begin{bmatrix}w_1\\...\\w_n\end{bmatrix}
$$
A tag sequence, $\vec{t}$, would look like...
$$
\vec{t}_{n\times1} = \begin{bmatrix}t_1\\...\\t_n\end{bmatrix}
$$
Given the below tag sequences...
$$
\begin{cases}
	\text{DET DET JIR NN NNS VBD}\\
	\text{DET NNS VBD DET JIR NN}\\
	\text{VBD JJR NNS DET NN DET}
\end{cases}
$$
.. which are the the most probable to occur?

The most probable tag sequence is calculated by...
$$
\underset{\vec{t}_{n\times1}}{argmax(P(\vec{t}|\vec{w}))}
$$
