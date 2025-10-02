[[1,1 - What is SQL]] <- Back

---
An SQL statement is structured like the following:
```SQL
CREATE TABLE module{
	moduleCode VARCHAR (5),
	moduleName VARCHAR (30) NOT NULL,
	moduleCedit INT NOT NULL DEFAULT 15,
	moduleConvenor VARCHAR (5),
	PRIMARY KEY (moduleCode),
};
```
NOTE: SQL statements not case sensitive.
- The reason some parts are capitalised and some are not is to denote separate parts of the statement.

## Creating a Table
To create a table, do
```SQL
CREATE TABLE tableName{

};
```

## Creating Attributes
Inside of a table, attributes can be created as a sequence of statements.
- Each statement creating an attribute will assign an identifier (attribute name), the data type of the attribute, and ANY constraints of that 