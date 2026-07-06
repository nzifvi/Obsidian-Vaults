[[6,1 - Homography & Perspective Transform]] $\leftarrow$ Back

---
# What is RANSAC?
RANSAC is an algorithm for fitting a model to data when you know some of the data points are outliers.
- Outliers considered as bad or noisy points.
- Inliers are data points considered to be good and not noisy.

Summarised idea: outliers can only accidentally agree with inliers model by chance.
- Fit model to a tiny, random subset of the overall data points.
- Check how many other points not in the tiny, random subset agree with the fitted model.
- A subset containing inliers will produce a model that most other inliers will agree with.


# Performing RANSAC
## 1) Sample minimally
Pick the smallest number of data points needed to uniquely define a model.
- For homography, 4 pairs are required.
- Let k denote the chosen number of data points.

Each point has an equal probability to be chosen.
$$
Data_{chosen} \subset Data
$$
$$
Data_{chosen} = \biggr\{x|x\in Data \wedge P(\text{x is chosen} = \frac{1}{|Data})\biggr\}
$$
$$
|Data_{chosen}|=k
$$
## 2) Train the model using only the chosen data subset.

## 3) Evaluate the model and store accuracy result

## 4) Do multiple times, creating a new $Data_{chosen}$

# 5) Choose model with best accuracy

