[[1,1 - What is SQL]] <- Back

---
DML provides a set of operations that enable data, stored in the database, to be manipulated in various ways.

# DML Reserved Words
## 1) INSERT
## 2) SELECT
SQL SELECT used to select data from an entity. More complex SELECT statements can result in data being selected from multiple entities. 
- Returns a table containing the selected data.

```SQL
SELECT
(<colName_1, ..., colName_k>)
FROM <tabName>;
```

$$
<colName_{1},...,colName_{k}> \in tabName
$$
- if using a * instead of a sequence of colNames, it will SELECT all from the given tabName entity.

### 2.1) PROJECTION
Projection is a modified variant of a SELECT statement which selects specific columns of a given entity.

$$
\pi_{(colName1,...,colName_{k})} = <colName_{1},...,colName_{k}>
$$
```SQL
SELECT
<colName_1,...,colName_k>
FROM <tabName>;
```

- Can be further enhanced using ```[DISTINCT]```, which results in duplicate record entries of an entity are not included.

```SQL
SELECT [DISTINCT]
<colName_1,...,colName_k>
FROM <tabName>;
```


### 2.2) CUSTOMISING SELECT RETURN TABLE
The table returned by a SELECT operation can be customised.
- Records can be ordered a certain way.
- Columns can be renamed to specific strings.

#### 2.2.1) ORDERING RECORDS
The records of a resulting table can be ordered. Even specific columns in the resulting table can be...
```sql
SELECT <columnName> AS <newNameForColumn>
FROM <tableName>
ORDER BY <rule>;
```

#### 2.2.2) RENAMING COLUMNS
Columns in the resulting table can be renamed by...
- Done using AS
```sql
SELECT <colName1> AS <newNameForColumn>
FROM <tableName>;
```

### 2.3) SELECT QUERY ORDER
The statements in a SELECT query must come in a structured way...
```sql
SELECT 'columns are selected'
vvv
FROM 'entites the columns come from are specified'
vvv
WHERE 'conditions are specified to filter the records in specified columns'
vvv
ORDER BY 'the records of the resulting table are ordered in a specific way'
```
## 3) JOIN
SQL ```JOIN``` is used to combine entities together in specific ways.
 
### 3.1) CARTESIAN PRODUCT (CROSS JOIN)
CARTESIAN product, using SQL ```CROSS``` allows for two or more tables to be joined into one.
- Can also have a ```SELECT``` applied to the cartesian product to only join specific attributes of an entity.


$$
\pi_{(colName1,...,colName_{k})} = <colName_{1},...,colName_{k}>
$$
```SQL
SELECT
<colName_1,...,colName_k>
FROM <tabName_1> CROSS JOIN <tabName_2>;
```

$$
x, x\in \pi_{(colName1,...,colName_{k})} | x\in tabName_{1} \oplus x\in tabName_{2}
$$

### 3.2) THETA JOIN (CONDITIONAL JOIN)
A theta join is a joining of two or more tables based on a given condition.
- The joining is conditional ON a given condition being true.

```SQL
SELECT 
*
FROM <tabName_1> JOIN <tabName_2> ON
<tabName_1>.<colName_1> <op> <tabName_2>.<colName_2>;
```
$$
colName_{1}\in tabName_{1} \wedge colName_{2}\in tabName_{2}
$$
- \<op\> is a given comparison operator

Multiple conditions can be chained together by use of AND

```SQL
SELECT 
*
FROM <tabName_1> JOIN <tabName_2> 
ON
<tabName_1>.<colName_1> <op> <tabName_2>.<colName_2>
AND
<tabName_1>.<colName_3> <op> <tabName_2>.<colName_4>;
```

A theta join ONLY works when the tables have a matching attribute between each other.
![[Pasted image 20260101170902.png]]

If attempting to perform a join where the involved tables do NOT have a matching attribute, it will not work.
- Suppose entity1 and 2 want to be joined. They have no matching connection (no direct relationship) THEREFORE a multijoin must be performed.
![[Pasted image 20260101171301.png]]

### 3.2) MULTI-JOIN
Multi-join is a special type of join which enables entities, without a direct connection, to still be joined into a singular table.
- Like building a bridge using one or more entities to form a connection between desired entities.
- Use when nothing is shared between 2 entities desired to be joined.
```sql
SELECT
	<attribute1>, <attribute2>, <attribute3>
FROM <table1>
JOIN <table1> ON <table1>.<attribute1> <op> <table2>.<attribute2>
JOIN <table2> ON <table2>.<attribute2> <op> <table3>.<attribute3>
```

## 4) INNER JOIN
`INNER JOIN` is a special type of `JOIN` statement.
- `INNER JOIN`, when joining tables, will NOT include any orphan records.
- Orphan records = a record which exists in one table but does not exist in another.
- `JOIN` will include these.

## 5) UPDATE
## &) DELETE
