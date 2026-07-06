[[7,2 - F1-Score]] $\leftarrow$ Back

---
# Problem: Data Sparseness
Many events, in the test data, will not have occurred in the training data.
- Because many events have a small probability to occur.

A feature, $f_j$, can never be seen in a document which was part of the training sample.
- Has to be accounted for.
- Solution to this problem is called SMOOTHING


# Solution: Smoothing
Smoothing is applied to estimated probability distributions.
- Multiple forms of smoothing exist.
- Simplest form is called add-one smoothing.

## Add-One Smoothing
When estimating $P(f|c)$, just add one to all counts.
- If a feature has never be seen with class c, it will have a count of 1 by default.

Can also smooth prior distributions.
- Usually not required.