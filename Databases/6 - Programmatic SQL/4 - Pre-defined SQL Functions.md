[[3,2 - Cursors]] $\leftarrow$ Back

---

# Aggregate Functions
## COUNT()
Count is a function which counts how many rows of a column, given as the parameter, meets a criteria.

```sql
COUNT(*) FROM <tableName> WHERE <statement>
```
- \* is used to select all rows matching the given statement in the WHERE part of the SELECT.
## MIN() / MAX()
Self explanatory
# TIMEDIFF()
`TIMEDIFF()` used to calculate the exact difference in time between two time values.
$$
TIMEDIFF(t_1, t_2) = t_1 - t_2
$$

```sql
TIMEDIFF(<time1>, <time2>)
```

# NOW()
`NOW()` returns the current time.
- Requires no parameters.