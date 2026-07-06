[[4 - Comparing Feature Descriptors]] $\leftarrow$ Back
[[]]

---
# Matching Features
Matching features is the process of finding equivalent features across multiple images.
- Same feature in 2 images will have the same feature descriptor.
- Identified by having equivalent, or approximately equivalent, feature descriptors.

Multiple methods exist in matching features across images. Some are...
1) Greedy Feature Matching
2) Others exist.

# Greedy Feature Matching
For every feature in image A, pick the feature in image B with the smallest descriptor distance, $L_2$.
- No global optimisation.
- Take locally best option each time.

```python
import cv2

bf = cv2.BFMatcher(
	cv2.NORM_L2,
	crossCheck = True
)
```

BFMatcher (brute-force matcher) is an object in opencv2.
- Compares every feature in A against every feature in B: looking for matching features.

crossCheck is a flag which controls whether the feature match is optimal.
- Checks if match occurs from both image A -> B and B -> A.

When matching features...
- Some matches will be outliers (false matches)
- Some matches will be inliers (true matches)