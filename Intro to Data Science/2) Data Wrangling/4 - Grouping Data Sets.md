[[3 - Merging Data Sets]] <- Back

---
# Grouping Data Sets
DataFrames can be split into groups based on one or more columns.
- Allows for subsections of a dataframe to be cut out.

## Grouping DataFrames with Pandas
The `groupby()` function member of DataFrame object and involves 1 or more following steps.
- Splitting: DataFrame is split into separate groups based on some condition(s).
- Applying: a function is applied to each group, produced by the splitting step, independently.
- Combining: the results of the functions applied are merged into one data structure and returned.

```python
pandas.DataFrame.groupby(
	by,
	axis,
	level,
	as_index,
	sort,
	group_keys,
	dropna
)
```

### Parameters 
- by
	- required.
	- 