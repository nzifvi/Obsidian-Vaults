[[1- Declarative SQL vs Programmatic SQL]] $\leftarrow$ Back
[[2,2,1 Procedural SQL]] <

---
# 1) What are Stored Procedures?
Stored procedures are routines and functions written in a block-structured, procedural language which is an add on to SQL.
- Most major Database vendors provide stored procedures when selling their database products.

# 2) Advantages of Stored Procedures

1) Performance:
	- Executed and optimised on the server where the database exists. 
	- Reduced data transfer.

2) Productivity & Ease of Use:
	- Shares business logic across all applications which access it.

3) Scalability:
	- Shared usability on the server. Servers can be scaled up to provide more performance if required.

4) Maintainability:
	- One group of functions are used rather than multiple groups existing. Easier to maintain one group rather than multiple groups which may all behave differently.


5) Interoperability:
	- Stored procedures are useable by multiple applications.

6) Replication:
	- Stored procedures can be used between multiple databases.

7) Security:
	- Stored procedures can have permissions assigned to them to prevent them from being executed when they should not be.