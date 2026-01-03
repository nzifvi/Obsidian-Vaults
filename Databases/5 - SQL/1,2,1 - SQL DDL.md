[[1,1 - What is SQL]] $\leftarrow$ Back
[[1,2,2 - SQL Types]] $\leftarrow$ Additional

---
DDL is used to define, or modify, a database and it's structure.
- Defines and names tables, attributes, relationships.
- Also allows constraints and integrity to be specified for attributes.

A data definition language allows for...
- Tables to be set up and altered.
- Domain constraints to be expressed.
- Integrity constraints to be expressed.
- Define default values for entries in the event no value is provided.
- Have database info stored in a data dictionary.

# DDL Reserved Words
## CREATE
```sql
CREATE TABLE <tableName> (
	"column definitions come first for an entity"
	<columnDef1>,
	<columnDef2>,
	...
	
	"then entity constraints come"
	<tableConstraint1>,
	...
);
```

### ColumnDef

columnDefs are used to define the attributes of an entity.
```sql
<labelName> <DataType> <columnConstraint>
```
Column constraints can be:
1) PRIMARY KEY
	- Used to specify that a given attribute is the primary key of an entity.

```sql
employeeID INT(8) PRIMARY KEY
```

2) UNIQUE
	- Used to specify that a given attribute must have unique values.

```sql
employeePhoneNumber INT(32) UNIQUE
```

3) NOT NULL
	- Used to specify that a given attribute cannot have a null value.

```sql
employeeFirstName VARCHAR(16) NOT NULL
```

4) CHECK
	- CHECK is used to specify that a given attribute meets a specified condition.

```sql
employeeAge INT(8) CHECK (employeeAge >= 18)
```

5) DEFAULT
	- DEFAULT column constraint sets a value automatically if a value isn't provided.

```sql
employeeAge INT(8) DEFAULT 18
```

### TableConstraint
Table constraints are constraints that apply to the entire entity, not just a single attribute.
- Come after column definitions.
- A table constraint may involve 1 or more columns.

1) Multiple PKs
	- When multiple PKs are required, such as when you have a composite key, a table constraint must be used to define them both as PKs.

```sql
studentID INT(32) NOT NULL,
module ID INT(32) NOT NULL,

PRIMARY KEY (studentID, moduleID)
```
- Same can be done for UNIQUE.

2) Foreign Keys
	- To create a FK and enforce a relationship between entities, an FK table constraint must be applied.

```sql
FOREIGN KEY (<attributeName>) REFERENCES <entityFKisFrom>(<attributeName>)
```

3) Perform checks using multiple columns.

```sql
minGrade INT(8),
maxGrade INT(8),

CHECK (minGrade <= maxGrade)
```

## ALTER
Alter allows for an existing entity to be modified as opposed to having to drop it and restart.
- Prevents existing data from being lost entirely by allowing entities to be modified whilst existing.

ALTER allows for...
- New columns to be added to entities.
- Existing columns to be removed from entities.
- Columns to be modified (properties and types).
- Entities to be renamed.
- Constraints to be added/removed from attributes of an entity.

```sql
ALTER TABLE tableName
<modificationClause(s)>;
```

### Adding Columns
To add a column to an existing Entity...
```sql
ALTER TABLE <entityName>
ADD COLUMN <attributeName> <attributeType>
...
ADD COLUMN <attributeName> <attributeType>; 
```

### Removing Columns
To remove, aka DROP, a column from an existing Entity...
```sql
ALTER TABLE <entityName>
DROP COLUMN <attributeNameToDrop>;
```
- Some DBMS's may not allow multiple columns to be dropped in a single statement.
### Modifying Columns
Modifying a column allows for it's type or column constraints to be modified.
- Column constraints: NOT NULL, UNIQUE, CHECK.

```sql
ALTER TABLE <tableName>
MODIFY COLUMN <columnNameToModify> <type> <columnConstraint>;
```

### Renaming Entities
To rename an entire table, aka entity, you...
```sql
ALTER TABLE <tableName>
RENAME TO <newTableName>;
```

### Adding/Removing Entity Constraints
Table, aka entity, level constraints can be added/removed.
- ADD to add, DROP to remove.

```sql
ALTER TABLE <tableName>
ADD CONSTRAINT <constraint>
```

```sql
ALTER TABLE <tableName>
ADD PRIMARY KEY (<pkName>);
```

### DROP
