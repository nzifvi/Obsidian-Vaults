[[1,1 - Tokenisation]] $\leftarrow$ Back

---
# Setup
```python
import nltk
from nltk.tokenize import sent_tokenize
from nltk.tokenize import word_tokenize

text = "Cats are running towards the walls. That's confusing"
sentences = sent_tokenize(text)

words = []
for sentence in sentences:
	tempList = word_tokenize(str(sentence))
	words = words + tempList
	
print(words)
```
# NLTK Lemmatisation

```python
from nltk.stem import WordNetLemmatizer

lt = WordNetLemmatizer()

for i in range(0, len(words)):
	words[i] = lt.lemmatize(words[i])
	
print(words)
```


