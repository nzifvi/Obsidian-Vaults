
---
# How to Determine if Residuals have Gaussian Distribution
The easiest way to check if some feature, such as residuals, has a Gaussian distribution is via a visual check.

3 Primary Visual Checks exist:
1) Scatter Plot
2) Q-Q Plot.
3) Histogram


# 1) Scatter Plot Visual Check:
Checking via a Scatter plot should be the first check. It tests the assumption of constant variance.
- For something to have a gaussian distribution, it must have constant or near constant variance.

![[Pasted image 20251230014259.png]]

Look for:
- Values should be distributed randomly.
- Values should be distributed consistently across the range of the independent variable the points come from.
	- NO STRUCTURE SHOULD BE VISIBLE OR APPROXIMATELY VISIBLE.

# 2) Q-Q Visual Check

# 3) Histogram Visual Check
By creating a histogram of the values that are being checked if they have a gaussian distribution are a good way to see if it indeed does have a gaussian distribution.
- Create n bins, defined by intervals.
- Increment counter in bins based on how many values fall into that bin.


Histogram should have/be...
1) Symmetrical, or approx. symmetrical, about a mean.
2) A central peak exists about the mean.
3) As you go further away from the central peak, bars get smaller. This represents the tails.

If above 3 conditions are met, values DO have a gaussian distribution.