[[1 - Importing and Loading Parts of Corpora]] $\leftarrow$ Back
[[3 - ConcatenatedCorpusView]] $\leftarrow$ Next

---
# What is a `StreamBackedCorpusView`
`StreamBackedCorpusView` is an object used to represent a single document that is part of a corpus.
- Functions like a Python list yet works differently.

`StreamBackedCorpusView` does not load entire file into memory. 
- Reads portion of document, that is accessed, into memory.

`StreamBackedCorpus` object is part of `nltk.corpus.reader` module.
- import `util` from `nltk.corpus.reader`
# Initialising `StreamBackedCorpusView` Objects

```

varName = util.StreamBackedCorpusView(
	file_path
	encoding
	read_func
)
```

#### file_path
file path of file desired to be loaded into `StreamBackedCorpusView` object.

## encoding
encoding style used in document.

## read_func
read_func determines how the document should be read. Can be equal to...
- `word_tokenize` - turns document into a `StreamBackedCorpusView` of words.
- `sent_tokenize` - turns document into a `StreamBackedCorpusView` of sentences.