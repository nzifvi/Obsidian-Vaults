[[5,1 - Distributional Semantics]] $\leftarrow$ Back
[[5,3 - Word Vectors]] $\leftarrow$ Next

---
# What are Context Windows?
A context window is a tool used to capture a target word's context so that the meaning of said target word can be inferred via how it is used.
- Works due to Distributional Hypothesis

A window has a size: how many words it will capture either side of the target word.

Given the sentence:
> "The cat sat on the warm mat"

Supposing cat is the target word
- Target word is the word we want to try and understand the meaning of

Let $Window_{size} = 1$

![[Pasted image 20260201135333.png]]

Features, and their frequency, added with target word cat:
$$
cat: \{(The, 1), (Sat, 1)\}
$$
$$
(Word, Freq(Word))
$$
Each tuple part of the features denotes:
- The word.
- The frequency.

Windowing identifies which words tend to appear near a given target word.
- Repeating windowing for a given target word, across a large corpus, will capture:
	1) Typical actions (verbs)
	2) Typical properties (adjectives)
	3) Typical objects/subjects
	4) Typical associations
WITHOUT any need for manual annotation.

