[[5 - Example of Top-down Approach]] <- Back
[[7 - Resolving Many to Many Relationships]] <- Next

---
## What are Keys?

An attribute of an entity can also be a key. What a key is depends on what type of key said key is.

The types of key are:
1) Candidate key
2) Primary key
3) Foreign key
4) Composite key

### Candidate Key
A candidate key is a set of the minimum attributes required to uniquely identify an occurrence of an entity type from all other occurrences.

### Primary Key
A primary key is an attribute selected to uniquely identify each occurrence of an entity type.
- Can be an id, email address, name, etc.

### Foreign Key
A foreign key is one, or more, attributes in an entity which is a primary key from another entity.

### Composite Key
A composite key is a type of key, consisting of 2 or more attributes, which together uniquely identify each occurrence of an entity.
- The attributes forming a composite key do NOT uniquely identify occurrences alone.

## Identifying Keys from Attributes
Given a relation, the keys of an entity can be established.

### Identifying Primary Keys
![[Pasted image 20250706144249.png]]

To identify a primary key, look for the row of attributes which has no duplicate attribute values.
- Attribute meeting this constraint becomes primary key.

studentID is the primary key (PK) for the Student entity.

Also apply common sense if the relation lacks enough information.
- Multiple people can have the same name, meaning it may not be unique.

### Identifying Foreign Keys
![[Pasted image 20250706144654.png]]
To identify a foreign key in an entity's attributes, you must be able to see the other relation, or the entire relation (assuming the example above is only a segment of an entire relation).

![[Pasted image 20250706144758.png]]

Because moduleID is the primary key of the Module entity, it will be a foreign key of ANY other entity it appears in as an attribute.
- This forms a RELATIONSHIP between entities.
- Without a foreign key in at least one of the involved entities, no relationship can exist.

### Identifying Composite Keys
Composite keys are only really formed when a m:m (many to many) relationship must be resolved.