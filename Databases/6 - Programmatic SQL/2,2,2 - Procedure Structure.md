[[2,2,1 Procedural SQL]] $\leftarrow$ Back

---
# 1) Creating a Procedure

```sql
DELIMITER <delimiterSymbol>

CREATE PROCEDURE <procedureName> (<params>)
BEGIN 
	<localVarDeclarations>
	<procedureBody>
END <delimiterSymbol>

DELIMITER;
```

## RULES:
1) Must specify delimiterSymbol, via ´DELIMITER´ reserved word, BEFORE creating procedure.
	- Once done defining procedure, use `DELIMITER` to reset the delimiterSymbol back to the default SQL one.

2) To define the procedure's body, nest it within BEGIN  and END \<delimiterSymbol\>

3) Local variables MUST all be declared before \<functionBody\>

# 2) Procedure Parameters
To specify a parameter for a procedure, follow the structure:
```sql
<mode> <paramName> <dataType>
```

## Mode
Parameter modes define how the parameter will be handled in the function. It defines if it is an input or an output.

Three modes exist:
1) IN
	- DEFAULT: if mode not specified, it will have mode IN by default.
2) OUT
3) INOUT

### IN
Parameter is passed by value from caller into the procedure.
- Procedure can read value and use param's value throughout procedure.
- Value is not changed in the caller.

### OUT
Mode is used to send data back to the caller.
- Parameter in OUT mode acts as a placeholder. Procedure loads a result into it.
- When procedure finishes, caller accesses what value has been assigned to param in OUT mode

### INOUT
INOUT mode allows for a caller to pass a value into a procedure and then later access it.
- Normally used to update an existing value in a caller via a procedure being called.

## paramName

## dataType