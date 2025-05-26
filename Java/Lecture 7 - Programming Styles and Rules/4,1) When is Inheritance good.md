---
Lecture7:
---

[[3,1) Cohesion]] <- Back

---
- Inheritance should ONLY be used when...
	1) Both classes (parent and subclass) exist within the same logical domain.

	2) Subclass is a PROPER SUBTYPE of the superclass.
		- i.e. a Car is a subtype of Vehicle so inheritance is good to use here.
		- Can be detected by multiple classes sharing shared fields (i.e. money) or being classified as the same thing (i.e. a vehicle, gun, medicine, etc).