[[2 - Document Vectors]] $\leftarrow$ Next

---
# What is a Vocabulary 
A vocabulary is a set of words which are present in a document or multiple documents.
- Vocabularies are required in many parts of NLP. Especially for constructing document vectors.

# Constructing a Vocabulary
Given a sequence of documents denoted as $\mathcal{D}$
$$
\mathcal{D} = <D_1,...,D_n>
$$
- Each document, D, itself is a sequence of words.
$$
D_i\in \mathcal{D} | D_i=<w_1,...,w_m>
$$

A vocabulary, $V$, is a set of all words which appear in a given sequence of documents.
- Produced by adding all unique words to a singular set.
$$
V'=V+f(D_i, V)
$$
$$
f(D_i, V)= \{x | x \in D_i \wedge x\cancel{\in} V\}
$$
```python
vocab = []
for document in documents:
	for word in document:
		if word is not in vocab:
			vocab.append(word)
```
