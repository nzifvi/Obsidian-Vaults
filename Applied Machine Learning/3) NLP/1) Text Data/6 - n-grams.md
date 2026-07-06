[[5,4 - Co-occurrence Matrix]] $\leftarrow$ Back

#NLP-TextData

---
# 1) What are n-grams?
n-grams are a continuous sequence of tuples which consist of words or characters derived from text/speech.
- n determines the order of the n-gram.
- the order of the n-gram determines how many elements will be in each tuple.

# 2) Producing n-grams
Given a list of words $W$
$$
W=<w_1,...w_n>
$$
A k-grams can be produced by...
- Let $G_k$ denote k-grams.
$$
G_k = \bigg< 
(w_1,...,w_k), ... (w_i,...,w_{i+(i+k)}),...
\bigg>
$$

In python, implemented with
```python
def generateNGrams(document:list, n) -> list:
	# assuming document already tokenised into list of words
	
	return [
		tuple(document[i:i + n]) for i i + 1
	]
```

# 3) Uses of n-grams
n-grams can be used in
1) language modelling
2) text prediction
3) sentiment and text classification.
	- n-grams capture word sequences.
	- can be used to classify text into categories or semantics.
	- make it easier to detect 
4) plagiarism detection.
5) speech recognition.