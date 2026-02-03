[[2 - Functional Dependencies]] $\leftarrow$ Back

---
# What is Normalisation?
Normalisation is a technique which produces a set of relations with optimal properties.
- Gets rid of all forms of anomalies.
- Results in good database design.

# Stages of Normalisation

## 1NF
Not about dependencies. Each attribute must be atomic (no muli-valued attributes in columns).

## 2NF
2NF means that, for all attributes, every non-primary key attribute is fully functionally dependent on the primary key.
- Each attribute of entity individually functionally depends on the whole primary key
If...
$$
A \rightarrow (B,C,D)
$$
Then...
$$
A \rightarrow B
$$
$$
A \rightarrow C
$$
$$
A \rightarrow D
$$
### Performing 2NF
To perform 2NF, partial functional dependencies are identified and created as new entities.

To identify partial functional dependencies, see if there are attributes which are NOT functionally dependent on the PK of the entity.
- Will depend on PART of the PK.
- Entities with 1PK are automatically in 2NF.

![[Pasted image 20260104205514.png]]

#### ALL TABLES ABOVE IN 1NF

$$
\{clientNo, propNo\} \rightarrow startDate
$$
$$
propNo \rightarrow (propAddress, ownerNo, ownerName)
$$
$$
ownerNo \rightarrow ownerName
$$

$$
Primary_{key} = \{clientNo, propNo\}
$$
Testing if propAddress, ownerNo, ownerName are functionally dependent on clientNo...
- $76 \rightarrow$ 6 Lawrence St. Glasgow
- $76 \rightarrow$ 5 Novar Rd, Glasgow

ONE INPUT HAS 2 OUTPUTS $\Rightarrow clientNo \cancel{\rightarrow} propAddress$. This means that propAddress has a partial dependency on the other attribute forming the PK.

ONCE PARTIAL DEPENDENCY IDENTIFIED, A NEW ENTITY MUST BE CREATED TO HOUSE THE ENTITY THAT IS CURRENTLY WITHIN AN ENTITY.
- Process called decomposition, which splits the schema.
- Creates new entity where the partial key becomes PK of it.
- Move ALL attributes dependent on that partial key.
- Partial key remains in old entity, becomes foreign key for new entity where it is PK.

![[Pasted image 20260104210834.png]]

#### ALL TABLES ABOVE IN 2NF
## 3NF
3NF means that all entities are in 2NF and there is no entity where a non-primary-key attribute is transitively dependent on the primary key.

Each attribute functionally depends on the primary key ONLY. No attribute is functionally dependent on anything else besides the PK.

### Performing 3NF
To identify transitive functional dependencies...
- Look through attributes. Are there attributes which depend on something else instead of the PK?

![[Pasted image 20260104211247.png]]

$$
propNo \rightarrow (propAddress, ownerNo, ownerName)
$$
Look for functional dependencies between the attributes supposedly functionally dependent on the PK.

In this case, test...
$$
propAddress \rightarrow ownerNo
$$
$$
propAddress \rightarrow ownerName
$$
$$
ownerNo \rightarrow ownerName
$$
Testing $propAddress \rightarrow ownerNo$
- 6 Lawrence St, Glasgow $\rightarrow$ CO93
- 5 Novar Rd, Glasgow $\rightarrow$ CO93
6 Lawrence St, Glasgow $\rightarrow$ CO93 $\wedge$ 5 Novar Rd, Glasgow $\rightarrow$ CO93 $\Rightarrow$ $propAddress \cancel{\rightarrow} ownerNo$

Testing $ownerNo \rightarrow ownerName$
- $CO93 \rightarrow$ Tina Murphy
- $CO20 \rightarrow$ Chris Newbank
- $CO40 \rightarrow$ David Brent
FUNCTIONAL DEPENDENCY FOUND: TRANSISITVE AS AN ATTRIBUTE DOES NOT DEPEND ON THE PK OF THE ENTITY.

To resolve a transitive functional dependency, do...
1) Move the attribute the other attributes functionally dependent on, as well as the functionally dependent attributes, into a new entity.
2) The attribute the others are functionally dependent on becomes PK of new entity.
3) The attribute the others are functionally dependent on remains in old entity and becomes a FK whilst all others are removed.

![[Pasted image 20260104212215.png]]
#### ALL TABLES ABOVE IN 3NF