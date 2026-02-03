
---
# 1) What is Sentence Segmentation?
Given a string, which could contain many sentences within that string, sentence segmentation breaks up that string into a list of sentences.
- Done via punctuational delimiters: denoting when a sentence ends.

> I want to go to the U.S.A. next Summer. Don't you? I want to go to the U.S.A. Don't you? I saw H.M.S. Victory in Portsmouth. It was impressive. "When shall we leave?" she asked.

Sentence segmentation, on the above string, would produce:
- I want to go to the U.S.A. next Summer.
- Don't you?
- I want to go to the U.S.A.
- Don't you?
- I saw H.M.S. Victory in Portsmouth.
- It was impressive.
- "When shall we leave?" she asked.

```python
from nltk.tokenize import sent_tokenize
string = "I want to go to the U.S.A. next Summer. Don't you? I want to go to the U.S.A. Don't you? I saw H.M.S. Victory in Portsmouth. It was impressive."
sentences = sent_tokenize(string)
```

# 2) Tokenisation
Once a string has been segmented into a list of sentences, the words part of the sentence should then be tokenised.
- Done via the built in `split()` function member of strings.

```python
tokens = []
for i in range(0, len(sentences)):
	tokens = tokens + sentences[i].split()
print(tokens)
```
