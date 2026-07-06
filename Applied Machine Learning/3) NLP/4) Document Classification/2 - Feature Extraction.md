[[1,2 - Document Classification Architecture]] $\leftarrow$ Back
[[3,1 - Classification Models]] $\leftarrow$ Next

---
# Words as Features
Words, within documents, act as evidence used to determine if a document is part of a given class.
- Word "evidence" acts as evidence that a document may have a positive meaning.
- Word "bitcoin" might act as evidence that an email is spam.

Key idea: treat a document as a bag-of-words.
- Ignore order and grammatical structure.
- Document must be pre processed to transform it into a bag of words.
- SOMETIMES ignore frequency, resulting in a document being treated as a set of words.

# Feature Representation
The features of a document, upon extraction, may be represented as...
#### 1) Binary-values.
$$
D1 = \biggr\{(cats: True), (mice:True), (the:True)\biggr\}
$$
Elements of extracted features are 2-tuples.
- 1 element of tuple is the feature.
- other element is a Boolean value indicating if the feature was present in the document.
#### 2) Numerically valued.

$$
D1=\biggr\{(cats:1), (mice:1), (the:2)\biggr\}
$$
Elements of extracted features are 2-tuples.
- 1 element of tuple is the feature.
- other element is an integer value indicating frequency of feature in document.
#### 3) Sparse Vectors.
Extracted features of a document can be stored in a vector, similar to word vectors.
- Each dimension represents an extracted feature in a document.
- The value of the rectangular component, in a sparse vector, is the frequency of that feature that dimension, the rectangular component is in, represents

$$
\vec{D1}= freq(cats)\hat{e}_{cats}+freq(mice)\hat{e}_{mice}+freq(the)\hat{e}_{the}
$$
Can store these vectors, from multiple documents, in a matrix.
- Each vector becomes a row vector.
![[Pasted image 20260207125245.png]]

When considering features which are not present, let their frequency equal 0.
- Still add new dimensions if they are encountered in a new document.