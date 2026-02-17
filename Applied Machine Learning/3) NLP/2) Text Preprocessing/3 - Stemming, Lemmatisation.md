[[2 - Normalisation]] $\leftarrow$ Back
[[4 - Parts of Speech]] $\leftarrow$ Next

---
# 1) What is Stemming?
Stemming is the process of removing unwanted affixes to a word.
- Does not require a lexicon/dictionary.
- Production rules, from CFGs, are used instead.

$$
ATIONAL \rightarrow AT
$$
$$
FUL \rightarrow e
$$
$$
SSES \rightarrow SS
$$
$$
\biggr\{ relational, relate, hopeful, caresses\biggr\}
$$
Applying stemming production rules to the set of words produces...
$$
\{relat, relate, hope, caress\}
$$

Stemming has complications:
- Errors of commission: false positives.
	- A word is wrongly stemmed when it is already an affix, due to a production rule.
- Errors of omission: false negatives.
	- A word is not in it's affix form. No production rule has been declared to stem it.

# Stemming in Python
Uses PorterStemmer: an object in nltk.stem.porter module which stems words.
```python
from nltk.stem.porter import PorterStemmer
stemmerObj = PorterStemmer()
words = []
stemmedWords = []
for word in words:
	stemmedWords.append(stemmerObj.stem(word))


```

# 2) What is Lemmatisation
Lemmatisation is another process applied to the result of stemming.

Stemming can, sometimes, create words which do not exist. Lemmatisation handles this by looking at the results of stemming and...
- Leaving them unchanged if the words are real.
- Replacing them with the real world if the result isn't a real one.

## Lemmatisation in Python
Uses WordNetLemmatizer from nltk.stem.wordnet module
```python
lemmatiser = WordNetLemmatizer()
words = []
lemmatisedWords = []
for word in words:
	lemmatisedWords.append(lemmatiser.lemmatize(word))
```
