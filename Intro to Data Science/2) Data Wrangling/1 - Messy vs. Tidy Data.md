[[2 - Tidying Data via Pandas]] <- Next

---
# What is classified as Tidy Data?
Data, when stored in some format, is considered tidy when...
- Each variable forms a column and contains values STRICTLY related to that variable.
	- Variable: a measurement or attribute (sex, age, height, etc).

- Each observation forms a row.
- Each type of observational unit forms a table.

# What is classified as Messy Data?
Data, when stored in some format, is considered messy when...
- Column headers are values, not just variable names.

![[Pasted image 20251006102034.png]]

- 2 columns contain a variable, treatment, but also contain the two possible outcomes of the treatment (a, b).
- Fixed by creating a singular column, which is for the variable.

![[Pasted image 20251006102237.png]]
