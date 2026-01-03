[[2,1 - About Stored Procedures]] $\leftarrow$ Next

---
# Difference between Declarative and Programmatic SQL
SQL is declarative.
- Good at retrieval and reporting.
- Not good for data processing.

Applications need a way to access SQL databases in a programmatic way.
- Achieved by use of SQL procedures.

Since SQL is declarative, it does not have...
- If-then-else branches.
- While loops and for loops.
- Go to.
- Variables which can be assigned a value.

- Applications need a way of passing non-constant values to a SQL database and having SQL use logical conditions or loops to return what has been requested.

Three solutions exist to this problem:
1) Extend SQL with procedures and make the SQL database handle their execution.
	- SQL will be upgraded with if-then-else branches, etc.
	- ADVANTAGES:
		1) Centralised handling of procedures in the SQL database avoids code duplication: multiple programs can avoid having identical statements.
		2) Reduced network overhead.
		3) It is possible to optimise the SQL database.

2) Embed SQL into the programming language of the application and allow the application to operate on returned SQL statements from the SQL database.
	- ADVANTAGES:
		1) Independent of the SQL database.
		2) Programmer can make their own choice of what language to use.
		3) Data can be controlled and cleaned before it even enters SQL database.

3) Provide an API which is independent of the database.
	- ADVANTAGES:
		- Refer to advantages of 2)

