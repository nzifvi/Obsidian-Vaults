[[3,3 - Speeded Up Robust Features]] $\leftarrow$ Back
[[3,5 - Deep Learned Feature Descriptors]] $\leftarrow$ Next

---
# What are Binary Robust Independent Elementary Features?
Binary Robust Independent Elementary Features, BRIEF, is a method of producing a binary feature descriptor.
- BRIEF calculates a binary feature descriptor to describe a window of an image about a feature.

Basic idea: do comparisons of pairs of pixels in a window about a detected feature
- Each element of a binary feature descriptor is the result of comparing two pixels (e.g. $I_{x,y} < I_{x,y+1}$)

