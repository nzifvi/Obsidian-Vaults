
---
## What is Data Cleaning?
Data cleaning = process of detecting and amending/removing data that is...
- incorrect.
- incomplete.
- improperly formatted.
- duplicated.

Cleaning is a required process for any real data.

Some examples of things to handle are...
- All values in a column should have a congruent data type.
	- No int in a column of floats, must be type casted back to a float.


## Handling NaNs

- If NaNs appear, the source of data must be consulted to understand WHY NaNs are appearing.
	- NaN values can be detected via `df.isna()` or `df.isnull()`
```python
nanIndices = df[df["column1"].isnull() | df["column2"].isnull()].index
```

- Requires a | as it is an element-wise logical OR operation.

```python
df.drop(nan_indices, inplace=True) # drops nan values only.
```

- Once dropped, reset the index to update the df.

```python
df.reset_index(drop=True, inplace=True)
```

## Handling duplicates
To check for duplicate values in a given column, you can use the `df.duplicated()` function member.
- Detect duplicates via their unique ID of their row.

```python
duplicateCount = df.duplicated(uniqueID)
if(duplicateCount > 0):
	# duplicates exist
else:
	# duplicates do not exist
```

Can also call `df.duplicated(uniqueID).any()` which just returns a true value IF any duplicates are detected.


To remove the duplicated data, their indices are required.
- Can be found by...
```python
pd.unique(df[df.duplicated(uniqueID)][uniqueID])
```
- returns a list of the indices of the duplicated data.

Typically, duplicates are copies of rows so all but one can be dropped.

However, sometimes, a row with a duplicate uniqueID can have conflicting data.
![[Pasted image 20251007121509.png]]
- Need to differentiate which one to keep.
	- Consult data source. They will let you know which to keep.

To then drop these duplicates bar one, you...
```python
df.drop_duplicates("Id", keep="last", inplace=True, ignore_index=True)
```
- Requires ignore_index to be assigned True.


