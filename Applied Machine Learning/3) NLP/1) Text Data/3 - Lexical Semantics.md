[[2 - Zipf's Law]] $\leftarrow$ Back
[[4 - Semantic Relationships]] $\leftarrow$ Next

---
# 1) Meaning of Words
Lexical semantics focuses on the meaning of a given word.

Lexicographers produce dictionaries which:
- Provide distinct meanings, aka senses, a given word can have.
- Provide definitions of each individual sense.
- Give examples of how different senses are used.

Problem: multiple dictionaries exist and disagree on how many different senses a word may have.

Machine readable dictionaries exist, allowing programs to use them:
- WordNet is one of them.

nltk.corpus module has a wordnet dictionary which has a `synsets()` function member.
- `synsets()` takes a word, in the form of a string, as a parameter and returns a list of synsets that word is a part of.
- EACH synset corresponds to a different, unique sense of the word.

```python
from nltk.corpus import wordnet
wordnet.synsets("hello")
```

A synset is an object which has function members.
- `definition()` is a synset function member which takes no parameters and returns the definition of that sense of the word.
# 2) Definitions
The definitions of a given word can be printed can be accessed by...
```
from nltk.corpus import wordnet
fireSynsets = wordnet.synsets('fire')
for index, sense in enumerate(fireSynsets):
	print("{}: {}".format(index+1, sense.definition()))
```


# 3) Homonyms
Given a word, n homonyms are different definitions of the word.
- Homonyms = same name in Greek.
- The meaning of the senses is very broad and different.

# 4) Homographs
?

# 5) Homophones
Homophones = same sound.
- Different words can have the same pronunciation but different spellings.
	- there, their
	- new, knew.

Homophonic words are a big problem for speech-input applications.

# 6) Polysemy
Polysemy means that a word has many senses.
- The senses are often related and referred to as metonyms.

# 7) Monosemy
Monosemy means that a word has a single sense.
- Very few words are truly monosemous in English.
- Some words have a predominant sense. This is different from monosemy as a predominant sense is just one more frequently meant when saying the word.