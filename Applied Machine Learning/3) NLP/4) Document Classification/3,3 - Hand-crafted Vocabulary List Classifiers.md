[[3,2 - Scoring Documents]] $\leftarrow$ Back
[[3,4 - Automatically Derived Vocabulary List Classifiers]] $\leftarrow$ Next

---
# Hand-crafted Vocabulary List Classifiers
A hand-crafted vocab list classifiers are a set of lists.
- Each list represents a class.
- The members of that list represent words which belong to the class their list represents.
- They are often fixed and small.
- Normally created BEFORE training and or inference.

Hand-crafted vocab lists come from early NLP systems, as well as specialised systems or systems which perform with domain-specific tasks.

Suppose 2 classes are defined:
- $L_{+}$ - words with positive meaning.
- $L_{-}$ - words with negative meaning.

A person would then add lists they believe or are told corresponds to the classes
$$
L_{+}=\biggr\{happy, joy, excited, cheerful\biggr\}
$$
$$
L_{-}=\biggr\{sad, mourning, despair, crying, sobbing, tears\biggr\}
$$
You would then be able to classify a document d based on...
- Scoring: [[3,2 - Scoring Documents]]
$$
class(d) = \begin{cases}
count(d, L_{+}) > count(d, L_{-}) + \delta \Rightarrow class(d) = "positive"
\\
count(d, L_{-} > count(d, L_{+}) + \delta \Rightarrow class(d) = "negative"
\end{cases}
$$

# Problems with Hand-crafted Vocab Lists

#### 1) Hard to build comprehensive lists
Hand-crafted vocab lists rely on people manually adding words. It relies upon them knowing what to add.
- Can miss out words that should be included.

#### 2) Domain-specificity
Vocabulary varies in definition across different domains. One word have another meaning in another domain.
- Hand-crafted vocab lists become incorrect.

#### 3) Variation in how people express themselves.

#### 4) Relevance of words not always obvious.