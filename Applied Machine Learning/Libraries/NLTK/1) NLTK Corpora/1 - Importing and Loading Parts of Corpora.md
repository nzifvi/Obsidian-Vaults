[[2 - StreamBackedCorpusView]] $\leftarrow$ Next

---
# Importing Corpora
To do anything with a corpus, it must first be imported.
- If it cannot be found, that corpus must be downloaded.

```python
import nltk
nltk.download('gutenburg') # downloads corpus by it's name
```

# Loading Parts of Corpora
Not ALL corpora have identical ways to load their contents.
- Some have function members which others do not.
- Some have different ways of loading their contents than others.

Corpora such as...
- gutenburg.
- brown.
- reuters.
- webtext.

have the following function members:
#### `raw()`
`raw()` function member returns the entire corpus as a string.
- IS NOT pre-tokenised. Tokenisation has to be applied during pre-processing.
#### `words()`
`words()` function member returns the entire corpus as a `StreamBackedCorpusView` OR a `ConcatenatedCorpusView`
- NOT A PYTHON BUILT-IN LIST.

`words()` results in the entire corpus being turned into a massive 1D list of the tokenised words.
- No sentence or paragraph structure. Just pure tokenised words.
#### `sents()`
`sents()` function member returns the corpus as a `StreamBackedCorpusView`

`sents()` preserves the structure of sentences.
- Elements act as sentences.
- Sentences are ALSO `StreamBackedCorpusView` type elements: a 1D array of tokenised words forming the sentence.

