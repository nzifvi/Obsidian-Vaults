[[1 - Vocabulary]] $\leftarrow$ Back
#NLP-Documents
---
# What are Document Vectors?
Document vectors provide a way to convert a document into a fixed-length numeric vector.

Document vectors require a vocabulary of a document to produce.

Let...
- $d$ denote a document.
$$
d=<w_1,..,w_n>
$$
- $count(w, d)$ denote the frequency of word $w$ in document $d$
$$
count(w, d, i)=\begin{cases}w=w_i \Rightarrow 1+count(w,d,i+1)\\w\cancel{=} w_i \Rightarrow count(w,d,i+1)\end{cases}
$$
- $V$ denote a vocabulary.
$$
V=\{w_1,...w_k\}
$$
	- vocabularies may have different sizes than a given document.
	- the size of the vocabulary used when converting documents into vectors determines the length of the vector.

Some types of document vectors are...
1) Bag-of-Words
2) Term Frequency-Inverse Document Frequency (TF-IDF)

# Bag-of-Words
Vocabulary $V$ is equal to...
$$
V=\{w_1,...w_k\}
$$
$$
|V|=k
$$
Each element of the bag-of-words vector represents the number of times a word in the vocabulary appears in the document.
- If word in vocabulary doesn't appear in document, corresponding element will have a value of 0.
$$
\vec{d}_{1\times k}=\begin{bmatrix}count(w_1,d)\\...\\count(w_k, d)\end{bmatrix}
$$
Bag-of-words vectors lose the word order present in the document the bag-of-words vector was built from.
# TF-IDF
Vocabulary $V$ is equal to...

$$
V=\{w_1,...w_k\}
$$
$$
|V|=k
$$
TF-IDF is similar to bag-of-words vectors. However, the words of TF-IDF vectors are weighted by importance.
- IDF component penalises words which appear frequently in a document. This allows less frequent words to be deemed as more important.
$$
TF(w, d) = \frac{count(w, d)}{size(d)}
$$
$$
IDF(w, \mathcal{D})=log\biggr(\frac{|\mathcal{D}|}{1+\sum_{i=1}^{|\mathcal{D}|}\biggr[count(w, d_i)\biggr]}\biggr)
$$
$$
\vec{d} = \begin{bmatrix}TF(w_1, d)\cdot IDF(w_1, \mathcal{D})\\...\\TF(w_{|V|}, d) \cdot IDF(w_{|V|}, \mathcal{D})\end{bmatrix}
$$
