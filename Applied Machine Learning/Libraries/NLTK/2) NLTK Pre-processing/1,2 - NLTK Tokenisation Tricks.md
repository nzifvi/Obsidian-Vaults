[[1,1 - Tokenisation]] $\leftarrow$ Back

---
# 1) Tokenising a List of Strings
Suppose you have a list of strings, or something similar, you can convert a python list to a string and then tokenise the strings.
- Return value of `sent_tokenize()` is a python list of strings.

2 possible methods exist:
1) replace string elements with lists of tokens: maintains a 2D list and preserves sentence structure.
2) tokenise the string elements and append the tokenised words into a new 1D list.

## 1) Replace String Elements with List of Tokens
```python
import nltk
from nltk.tokenize import sent_tokenize
from nltk.tokenize import word_tokenize

text = "3.14 is an approximation of Pi. Different decimal place precisions can be used."
sentences = sent_tokenize(text)
print(type(sentences))
print(sentences)
```

Above returns list of lists. Each element represents a sentence.
- MUST convert them to a str, via type casting, for `word_tokenize()` to work.

To tokenize each sentence...

```python
for i in range(0, len(sentences)):
	sentences[i] = word_tokenize(str(sentences[i]))
	
print(sentences)
```

## 2) New 1D List of Tokens
```python
sentences2 = sent_tokenize(text)
print(type(sentences2))
print(sentences2)
```

Above returns a list of lists. Each element represents a sentence.
- MUST convert them to str, via type casting, for `word_tokenize()` to work.

To tokenize each sentence and add the contents to a 1D list...

```python
words = []
for sentence in sentences:
	tempList = word_tokenize(str(sentence))
	words = words + tempList
	
print(words)
```

ALL structure is lost and there are a mixture of junk punctuation from the list's conversion to a string AND punctuation from the sentence.
- Lemmatisation is recommended.

# 2) Removing Duplicates from Word List
To remove duplicates from a list of words, cast it as a set...
```python
words = set(words)
print(words)
```

- Does not get rid of punctuation.
- Order of tokens, from the sentence they were tokenised from, will be lost
