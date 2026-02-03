[[5,2 - Context Windows]] $\leftarrow$ Back
[[5,4 - Co-occurrence Matrix]] $\leftarrow$ Next

---
# What are Word Vectors?
Word vectors are formed, by context windowing, and are a vector of a given word.
$$
Cat:\{(The, 1), (sat, 1)\}
$$
$$
\vec{cat}=Freq(The)\hat{e_{The}} + Freq(sat)\hat{e_{sat}}
$$
Each feature is it's own dimension: $\hat{e_{The}}$ denotes the "The" dimension.
- Each dimension has semantic meaning: a feature discovered via windowing.

The rectangular components of a word vector are:
- The dimension of a feature
- The value of a given rectangular component, in a given dimension, is the frequency that feature appears

