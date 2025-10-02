[[6 - Keys]] <- Back
[[8 - Data Dictionary]]

---
## What is the Problem with Many to Many Relationships?
![[Pasted image 20250706145340.png]]
Many students enrol on many courses (m:m relationship between students and courses)

m:m relationships can cause data duplication. The same data might be repeated in both entities of the m:m relationship.

m:m relationships can also result in incorrect associations when trying to use SQL to aggregate/calculate data.
- Records from entities may be missed or included incorrectly.

Many other issues are also caused by m:m relationships. Henceforth, they are resolved (transformed into another form).

## Resolving Many to Many Relationships
The solution is to create a new entity, connected to the two entities in a m:m relationship.
- This removes the m:m relationship, replacing it with a 1:m relationship between the new entity and both entities previously in an m:m relationship.

![[Pasted image 20250706175329.png]]

The new entity, resolving the relationship, will be formed of a composite key of both the primary keys of the two previous entities in the m:m relationship.

