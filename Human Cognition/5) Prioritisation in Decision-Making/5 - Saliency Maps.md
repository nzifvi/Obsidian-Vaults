[[4,2 - Hemispatial Neglect]] $\leftarrow$ Back

#DPHC-Attention #DPHC-Models 

---
# 1) What are Saliency Maps?
Saliency maps are a computational model which encodes how attention grabbing each location in a visual scene is.
- Model of exogeneous attention. [[2,1 - Exogenous Attention]] $\leftarrow$ Related
- Inspired by early computer vision approaches.

# 2) Saliency Map Model Architecture
Model operates in several hierarchical stages:
1) Multi-scale Feature Extraction
2) Centre-Surround Differences.
3) Normalisation and Conspicuity Maps
4) Saliency Map Formation
5) Winner-Takes-All Attention Deployment

## 1) Multi-Scale Feature Extraction
The input image is processed through linear filtering at 8 different spatial scales to extract 3 types of features.

The 3 types of extracted features are...
1) Colour in the form of (R,G,B,Y) channels
2) Intensity (ON/OFF contrast)
3) Orientation.

## 2) Centre-Surround Differences
Model computes centre-surround differences for each type of feature (the 3 features).
- Centre-surround differences mimic receptive fields in the primary visual cortex.

Mathematically expressed as...
$$
\text{FeatureResponse}(x, y) = |\text{Centre}(x,y) - \text{Surround}(x,y)|
$$

Centre-surround differences can be used to highlight locations in an input image where a value of a given feature differs significantly from other values of the same feature.
- A red object on a green background.
- Bright spot in a dark region.
- Vertical line among horizontal ones.

Centre-surround difference process produces 7 feature maps per feature type.

## 3) Normalisation and Conspicuity Maps
Each feature map, produced via the centre-surround differences stage, have 3 operations applied to them sequentially. 

1) Feature map is normalised to ensure comparable ranges.
2) 10 rounds of iterative filtering: suppresses noise and enhances strong activations.
3) Linear combination is applied

Let S denote the saliency map
$$
S=\begin{bmatrix}
s(1,1)&...&s(n,1)\\
...   &...&...\\
s(1,n)&...&s(n,n)
\end{bmatrix}
$$
- $s(x,y)$ denotes the saliency at position x, y of an image.

$$
s(x,y)=
$$