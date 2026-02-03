[[1 - Sentence Segmentation]] $\leftarrow$ Back
[[3 - Stemming, Lemmatisation]] $\leftarrow$ Next

---
# 1) Case Normalisation
Case normalisation means that, for each token, you convert upper case characters in the lexeme into a lower case one.

Advantages:
- Reduces number of target words:
$$
\{(The, 1),(the, 1)\}
$$
Applying case normalisation...
$$
\{(the, 2)\}
$$
- Increases the frequency of features.

Disadvantages:
- Increases ambiguity as case is used to indicate names and sometimes nouns in sentence.

## Example in Python
```python
sentence1 = "A long time ago in a galaxy far far away"
tokens = sentence1.lower().split()
print(tokens)
```

# 2) Number Normalisation
Number normalisation means that, for each number encountered in a sentence, it is replaced with the string NUM or something else.
- Done to remove extremely rare words, as numbers often account for a lot of them in a corpus.

```python
tokens = "In 2018 , there are 157 undergraduates taking NLE .".split()
for i in range(0, len(tokens)):
	if tokens[i].isdigit():
		tokens[i] = "NUM"
		
print(tokens)
```

# 3) Other Types of Normalisation
Normalisation is often applied to other rare words. These rare words might be...
- Names.
- Scientific or other terminology.
- Spelling errors or other errors.

It is common to ignore rare words. There are ways to do this:
- Use a lower frequency threshold.
- Consider top n most frequent words only.