
# 1:M, M:M relationships
## 1:M Relationships.
- The entity on 1 side of relationship known as parent entity.
- Entity on m side of relationship known as child entity.

Primary key of parent will be a foreign key in child.

![[Pasted image 20251229195142.png]]

```
Customer(__customerNo__)
primary key(customerNo)

Product(__productNo__, customerNo)
primary key (productNo)
foreign key customerNo references Customer(customerNo)
```
## M:M Relationships.
To handle M:M relationships...
- New entity is made.
- New entity typically named after the M:M relationship.
![[Pasted image 20251229195212.png]]
```
Branches(__branchID__)
primary key (branchID)

Employee(__employeeID__)
primary key (employeeID)

Has(__branchID__, __employeeID__)
primary key(branchID, employeeID)
foreign key branchID references Branch(branchID)
foreign key employeeID references Employee(employeeID)
```

This creates a COMPOSITE KEY.
- Composite key is the combination of two primary keys, which are also foreign keys in the entity used to resolve the M:M relationship, which uniquely identifies the participating entities.

