[[3,3 - Hand-crafted Vocabulary List Classifiers]] $\leftarrow$ Back
[[4,1 - Naïve Bayes Classifiers]] $\leftarrow$ Next

---
# Automatically Derived Vocabulary List Classifiers
Automatically derived word list classifiers are a supervised learning approach.
- Involves multiple steps
- Classes MUST be still specified by a person.

A set of documents forms two sets: training and testing documents.
- Both documents are tokenised into sentences and then individual words.
- Words are normalised: apply case and numeric normalisation.
- Punctuation and stop-words are removed.
- Lemmatisation is applied.

EACH document is labelled with what class it belongs to: done for training and testing
- Make each element a (document, class) pair.

$$
Documents_{Train}
$$
$$
Documents_{Test}
$$
- Normal splits for $|Documents_{Train}|$ : $|Documents_{Test}$ ratios are 50:50, 80:20, 90:10


Token lists are then converted into a feature representation (sparse vector representation, etc [[2 - Feature Extraction]])

Training set is used to build the model.
- An algorithm is used to select words, adding them to the specified class lists.

The testing sample is used to test how well the model performs.
- Proper use of training and test data is required to prevent over-fitting data.
- Low over-fitting crucial for model to work well with unseen data.

# How to determine if words are part of a class
Multiple approaches exist in determining what words belong to what specified classes.

## 1) Most Frequent Terms
During training, the classification of a document is known. Assign the MOST frequent terms in a document of classification x to class x.
- Let $tokenise(d)$ produce a token of words. Assume data is processed.
- ONLY add the most frequent terms (MUST SPECIFY A THRESHOLD OF FREQUENCY)
$$
class(d)=positive \Rightarrow L_{+}= tokenise(d)
$$

## 2) Greatest Frequency Difference
Consider a word w in document d. 
- Defining a new scoring option: greatest frequency difference.

Greatest frequency difference of a word w for class c is the total frequency of word w, in documents of class c, minus total frequency of word w in documents which are not class c.
- $D_c$ : documents of class c
- $D_{\not c}$  : documents not of class c

Let $score_{delta}(w)$ denote the greatest frequency difference score of word w.

$$
score_{\Delta}(w) = count(w, D_{c}) - count(w, D_{\not c})
$$
Word list for class c, $L_c$, are words with greatest frequency different scores for class c.


