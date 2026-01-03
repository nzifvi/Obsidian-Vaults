[[2,1 - About Stored Procedures]] <- Back
[[3,1 - SQL Programming Concepts]] $\leftarrow$ Next

---
# 1) Intro to Procedural SQL
Procedural SQL provides constructs very similar to those found in most high-level languages.

Provides...
1) Variable assignment.
2) Loops.
3) Conditional branches.

## 1,1) SQL Procedures
An SQL procedure is an action. A procedure's purpose is to change the state of the database.
- Could `INSERT` records into DB. 
- Could be used to remove records from DB.

## 1,2) SQL Functions
An SQL function doesn't change DB's state. It just interacts with it to produce something and return it. 
- Queries.
- Calculating values using data within the DB.

## 1,3) When to use Procedures or a Function
- Use procedures to automate `INSERT`, `DROP`, or other actions which are used to update/change the DB.
- Use functions to produce queries, via `SELECT`, or calculate values using data within DB.

# 2) Variable Declarations
Variables can be...
1) User defined:
	- Prefix the variable name with an @.

```SQL
SET @varName = ...;
```

2) Local variables:
	- Local variables declared within a procedure or function.
	- Can be parameters passed to the procedure/function OR declared within the procedure/function.

## Parameter and Local Variable Declaration
Parameter declarations depends on if you are declaring parameters for functions or procedures:
- [[2,2,2 - Procedure Structure]]
- [[2,2,3 - Function Structure]]

Local variable declaration is the same for BOTH functions and procedures.
- Local variables declared via `DECLARE` reserved word.

```sql
BEGIN
	DECLARE <var1Name> <dataType>;
END <delimiterSymbol>
```

Can specify a local variable to have a default value which acts as an initialisation.
- Done by using `DEFAULT` reserve word.
```sql
BEGIN
	DECLARE <varName> <dataType> DEFAULT <value>
```

## Variable/Parameter Assignment
To assign a value to a given variable/parameter, use `SET`:

```sql
DECLARE x INT DEFAULT 0;
SET x = x + 2;
```