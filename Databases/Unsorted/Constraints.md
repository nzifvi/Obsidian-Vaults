
---
Constraints are applied to relationships between entities and controls how entities can behave/exist within a relationship between each other.

## Structural Constraints:
Constraints placed on entity types which are members of a relationship.

Some structural constraints are:
- Cardinality Constraints.
- Participation Constraints.
- Multiplicity Constraints.


### Cardinality Constraints
Cardinality constraints will constrain how many entities may exist per other entity.
- 1:1, m:m, etc.

### Participation Constraints
Participation constraints constrain if an entity must be defined in a relationship with another.
- An entity's foreign key cannot be null in the entity it is related with.
- E.g: an employee MUST have a place of work.

Types of possible participation constraints are:
- Optional
- Mandatory

### Multiplicity Constraints
A multiplicity constraints combines info from both cardinality and participation constraints.

Denoted as (a, b)
- a is the cardinality and participation constraint for 1 entity.
- b is the same for the other.

If either = 0, that entity is optional.
If either != 0, that entity is mandatory.
- If either = \*, that entity is considered as infinity cardinality(many)
- Otherwise it is the precise integer value of the cardinality constraint.


### Rules for Structural Constraints
Use either cardinality and participation constraints or multiplicity constraints.
- Do not use both at same time.


