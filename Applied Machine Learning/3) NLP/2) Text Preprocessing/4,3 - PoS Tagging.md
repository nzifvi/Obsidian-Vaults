[[4,2 PoS Problems]] $\leftarrow$ Back
[[4,4,1 - PoS Tag Sequences]] $\leftarrow$ Next

---
# Info Sources for PoS Tagging
Below 2 properties of a word can be used as clues to a given word's tags.
- Word identity (likelihood of a tag given a word)
- Adjacent PoS tags (likelihood of a sequence of tags)

# Word Identities
A word, $w$, may have many possible PoS tags.
- Not all PoS tags are equally likely to be word's tag.

Tag probability distributions for words are often low entropy:
- One tag is far more likely than the other possible tags.


## Unigram PoS Tagger
One method of tagging is to find. Let...
- $T$ denote the set of all possible tags.
- $t\in T$ where t is a tag part of the set of all possible tags.
- $w$ is a word being PoS tagged.
$$
P(t|w)
$$
- probability of a tag given a word...

$$\text{tag}(w) = \underset{t\in T}{\text{argmax}} \, P(t|w) $$
$$
\underset{t\in T}{\text{argmax}} \, P(t|w) \ = argmax\biggr(P(t_1|w),...,P(t_n|w)\biggr)
$$

The probability of a tag given a word is equal to...
$$
P(t|w)=\frac{\text{number of occurrences of w tagged as t}}{\text{number of occurrences of w}}
$$
