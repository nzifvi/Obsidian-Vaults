[[4 - Grouping Data Sets]] <- Back

---
## What is Encoding?
Encoding is the act of transforming the values of entries from strings to a unique numeric value matching that still denotes the same thing.
- Let a column called gender have 2 possible values: "male" and "female"
- Encoding would consist of replacing all male entries with a numeric value denoting male.

Encoding is done for statistical operations which only work with strings.
- Especially needed for programs.


## How to encode in pandas DataFrames.
Let a column, sex, exist in a dataframe.
Let the column "sex" have 2 possible outcomes: "male", "female"

```python
df["sex"] = df["sex"].map(
	{"male": 1, "female": 0}
)
```

Could then use a function which translates a given numeric value to a string equivalent to translate the encoding.
- Can also just create a new column for the encoded equivalents.

```python
df["encodedSex"] = df["sex"].map(
	"male": 1,
	"female": 0
)
```
