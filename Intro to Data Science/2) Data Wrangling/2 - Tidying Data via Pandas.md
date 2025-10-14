[[1 - Messy vs. Tidy Data]] <- Back
[[3 - Merging Data Sets]] <- Next

---
## Pandas Melt Function Member
Pandas `melt()` function member is used to transform a DataFrame object into long format.
- a DataFrame in long format is a standard structure and is easier for computers to handle.
- Long format means that, for a given DataFrame...
	1) One or more columns become identifier variables.
	2) All other columns are then considered as measured variables and are unpivoted to the row axis.
	- Effect: ?