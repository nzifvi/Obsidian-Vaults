[[1,1 - What is Document Classification]] $\leftarrow$ Back
[[2 - Feature Extraction]] $\leftarrow$ Next

---
# Document Classification Architecture
![[Pasted image 20260206170105.png]]

Components:
1) Feature Extractor
2) Classifier

## Feature Extractor
A document is given as input to the feature extractor. Feature extractor transforms the document into a features vector.
- Can also be a set of features.


## Classifier
Classifier is fed a vector or set of features and, using a model which defines what features to expect in n given classes, determines which class is the most probable classification.