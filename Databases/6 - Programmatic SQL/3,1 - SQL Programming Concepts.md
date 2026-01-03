[[2,2,1 Procedural SQL]] $\leftarrow$ Back
[[3,2 - Cursors]] $\leftarrow$ Next

---
# 1) Conditionals

If-elseif-else chain:

```sql
IF <condition> THEN
	<statements>;
ELSEIF <condition> THEN
	<statements>;
ELSE
	<statements>;
END IF;
```

Switch statements:

```sql
CASE <variable>
	WHEN <value1> THEN <statements>;
	WHEN <value2> THEN <statements>;
	ELSE <statements>;
END CASE;
```

- When variable = value1, corresponding statements are executed.
# 2) Loops

While loop structure:
```sql
WHILE <condition> DO
	<statements>;
END WHILE;
```

Example of  while loop:
```sql
DECLARE counter INT DEFAULT 1;
WHILE counter <= 10 DO
	SET counter = counter + 1;
END WHILE;
```

