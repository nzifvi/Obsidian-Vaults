[[4,1 - Bayesian Decision-Making]] $\leftarrow$ Back

---
# Natural scene statistics
Natural scene statistics, NSS, refers to the problem of characterising...
- Edges
- Textures
- Subtle patterns of shading.
... from a wide range of structures.

![[Pasted image 20260304140457.png]]

# Predictive Coding
Predictive coding = efficient way to signal info with high redundancy.
- PC proposes visual system decorrelates visual inputs by coding for prediction errors.
- Prediction errors calculated by taking difference between a pixel and the linear weighted sum of it's neighbours.

Rao & Ballard's predictive coding model is a computational model of how visual cortex system works.
- Predictive coding can model how perceptual inference works.

Rao and Ballard's model is hierarchical: similar to how visual cortex is also hierarchical.
- Higher levels dedicated to increasingly complex features.

## Predictive Coding Model
![[Pasted image 20260305115937.png]]

Each level of hierarchy tries to predict inputs to level below.
- Implemented as predictive estimator. 

At each level, an error signal is fed forward to the next layer and a prediction is fed down to the prior layer.

### Predictive Estimators
Predictive estimators used to calculate predictions.
- Generate predictions about what input at the same layer will be.
- Generates predicted input based on prior experience and knowledge.

## Uses of Predictive Coding
Communicating prediction error, rather than raw info, is a efficient way to signal info with high redundant info.
- Images have lots of redundant info.

Calculating prediction errors means that visual system decorrelates visual inputs.
- Decorrelating visual input means what is common between multiple inputs is removed.
- This is why predictive coding model is more efficient.