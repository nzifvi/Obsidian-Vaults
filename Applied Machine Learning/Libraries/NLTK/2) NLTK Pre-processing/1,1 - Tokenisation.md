[[1,2 - NLTK Tokenisation Tricks]] $\leftarrow$ Related
[[2 - Lemmatisation]] $\leftarrow$ Next

---
# Tokenisation with NLTK
Multiple tokenizer objects exist in NLTK:
- `sent_tokenize()` - object used to tokenize sentences from paragraphs.
- `word_tokenize()` - object used to tokenize words from sentences.

Sometimes, when loading things from NLTK corpora, the sentences will automatically be tokenized.
- Other times, they will not be.

# `sent_tokenize()`
`sent_tokenize()` is an object which, given a string variable, will tokenize that string variable into a list of sentences.
- return value is a python list of sentences.
- from `nltk.tokenize` module.

`sent_tokenize()` is more advanced than just looking for periods as end of sentences.
- "Dr. Strauss" is not 2 sentences, it is an abbreviation.
- "3.14" is not 2 sentences, it is a decimal.
- many other cases where punctuation does not mean 2 sentences.

a simple algorithm which hunts down periods would fail at tokenising a string into sentences.
- `sent_tokenize()` accounts for such exceptions: safely tokenising a string for sentences

```python
import nltk
from nltk.tokenize import sent_tokenize

text = "3.14 is an approximation of Pi. Different decimal place precisions can be used."
sentences = sent_tokenize(text)
print(type(sentences))
print(sentences)
```

# `word_tokenize()`
`word_tokenize()` is an object which, given a string as input, will tokenize that string into a list of words.
- return value is a python list of tokenised words from the string input.
- from `nltk.tokenize` module.

The elements of the list, produced by `word_tokenize()` will ALSO split abbreviations, such as i'm into i and 'm
- Elements of list SHOULD be lemmatised to try and reconstruct words.

```python
from nltk.tokenize import word_tokenize

sentence = "Hello i'm Ben, it is nice to meet you"

words = word_tokenize(sentence)

print(type(words))
print(words)
```

