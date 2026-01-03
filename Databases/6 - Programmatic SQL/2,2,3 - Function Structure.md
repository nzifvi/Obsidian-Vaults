[[2,2,1 Procedural SQL]] $\leftarrow$ Back

---
# 1) Creating a Function
```sql
DELIMITER <delimiterSymbol>

CREATE FUNCTION <funcName> (<params>) RETURNS <returnType>
BEGIN 
	<localVarDeclarations>
	<functionBody>
END <delimiterSymbol>

DELIMITER;
```

## RULES
1) Must specify delimiterSymbol, via ´DELIMITER´ reserved word, BEFORE creating function.
	- Once done defining function, use `DELIMITER` to reset the delimiterSymbol back to the default SQL one.

2) To define the function's body, nest it within BEGIN and END \<delimiterSymbol\>

3) MUST return a value at the end of a function, matching the specified returnType, using the `RETURN` reserved word.

4) Local variables MUST all be declared before \<functionBody\>
# 2) Function Parameters
To specify a function parameter, follow the structure:
```sql
<paramName> <dataType>
```
- Parameter modes ONLY for procedure parameters. They do not exist for function parameters.