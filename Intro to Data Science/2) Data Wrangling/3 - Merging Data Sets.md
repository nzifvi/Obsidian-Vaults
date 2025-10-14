[[2 - Tidying Data via Pandas]] <- Back
[[4 - Grouping Data Sets]] <- Next

---
## Merging Data Sets
Sometimes, for n data sets, we may want to...
1) Outer join them: take their set union.
	- All available columns are kept. Columns of data set are merged and entries which did not previously have the newly added columns are given NaN values.


2) Inner join them: take their set intersection.
	- Leaves what the sets have in common, disregarding what they do not share.

NOTE: Additional set merge types are available (left join, right join).


## Merging DataFrames with Pandas
n dataframes can be merged using the `merge()` function member.
- takes 3 parameters.
- equivalent to SQL style operations, joining dataframes together.

```python
pd.merge(
	df1,
	df2,
	how = mergeType
	on = ?
)
```

- df1, df2 are the dataframes to merge.
	- Multiple can be merged, in series, by recursing merge:
	```python
	pd.merge(
		df1,
		pd.merge(
			df2,
			df3,
			how = mergeType
			on = ?
		),
		how = mergeType,
		on = ?
	)
	```

- how is the parameter controlling the type of merge performed on the given dataframes.
	- how = 'outer' causes outer join (UNION).
	- how = 'inner' causes inner join (INTERSECTION).