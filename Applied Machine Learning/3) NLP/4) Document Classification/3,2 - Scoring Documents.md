[[3,1 - Classification Models]] $\leftarrow$ Back

---
# Scoring Documents: Occurrences
A document, d, is treated as a bag of words.
- A word, w, is part of a document d.

The number of occurrences, aka frequency, of word w in document d is denoted as...
$$
count(d, w)
$$

If a document is tokenised into a list of words, you can calculate a list of frequencies, of given words, by...
$$
count(d, L)=\sum_{w\in L}\biggr[count(d, w)\biggr]
$$

# Scoring Documents: Sentiment Analysis
Let the word lists...
- $L_{+}$ denote a list of words with positive sentiment.
- $L_{-}$ denote a list of words with negative sentiment.
Such that...
- $count(d, L_{+})$ denotes the occurrences of words in worst list $L_{+}$ (words with positive sentiment)

Let $\delta$ denote a tolerance margin.

The class of a document can be obtained by...

$$
class(d) = \begin{cases}
count(d, L_{+}) > count(d, L_{-}) + \delta \Rightarrow class(d) = "positive"
\\
count(d, L_{-} > count(d, L_{+}) + \delta \Rightarrow class(d) = "negative"
\end{cases}
$$

# Options of Scoring
Different options exist for scoring words which occur in documents.

#### 1) Frequency
The score of a word w, $score(w)$, is equal to $count(w)$

#### 2) Uniform Score
Uniform scoring awards a score of 1 to a word w as long as it occurs in a document D.
$$
\forall w, w\in D \Rightarrow score(w) = 1
$$

#### 3) Weighted by Importance
Weighted scoring scores a word based on it's count, multiplied by the importance of a word.
- Importance weights have to come from somewhere (some process or user-defined).

$$
\forall w, w\in D \Rightarrow score(w) = importance(w) \cdot count(w)
$$
