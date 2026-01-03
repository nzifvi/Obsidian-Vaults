
# Entities to Schemas
Each entity type becomes a schema.
- Schema attributes are the entity's attributes.

![[Pasted image 20251229181428.png]]

Each entity has a relational schema: textual representation of the Chen ERD diagram.
- Structured like...
```
EntityName(
	entityAttribute1
	...
	entityAttribute(n)
)
```

# Symbol Meanings

## Entity

![[Pasted image 20251229181747.png]]

## Weak Entity

## Single-value Attribute
Multiple types of single-value attributes exist...

A basic single-value attribute looks like:
![[Pasted image 20251229181806.png]]

### Key Attribute

#### Primary Key
Text of the attribute will be underlined.
- Same in entity's relational schema.
![[Pasted image 20251229181927.png]]
```
Entity(
    __Attribute1__
)
```

#### Foreign Key
To specify a foreign key, do...
- Entity2 has an FK of Entity1.
```
Entity1(
	__Entity1Attribute1_
)

Entity2(
	__Entity2Attribute1__
	Entity1Attribute1
)

foreign key Entity1Attribute2 references Entity1(Entity1Attribute1)
```

## Multi-value Attribute

![[Pasted image 20251229182355.png]]

## Derived Attribute

![[Pasted image 20251229182423.png]]

# Relationships

## Strong Relationship
Strong relationships:
- Entity can exist independent of the other entity which it is in a relationship in.
- Entity can be uniquely identified without the other entity.

![[Pasted image 20251229182526.png]]

## Weak Relationship
Weak relationships:
- 
![[Pasted image 20251229182531.png]]

## Mandatory Relationships
Denoted as a straight, constant line between entities:
![[Pasted image 20251229194637.png]]

## Optional Relationships
Denoted as a dotted line between entities:
![[Pasted image 20251229194651.png]]

# Cardinality

## 1:1
![[Pasted image 20251229194326.png]]

## 1:M
![[Pasted image 20251229194338.png]]


## M:M
![[Pasted image 20251229194347.png]]
