[[4 - Approaches to Database Design]] <- Back
[[6 - Keys]] <- Next

---
## Scenario
Each school at a university has a number of lecturers and offer a variety  
of courses. Students enrol on a course and each course has a number  
of modules. A module is taught by one lecturer, but a lecturer may  
teach a number of modules, and most lecturers will also advise a group  
of students. Although a lecturer may sometimes teach a module on a  
course from any school, they are employed by one, their school. Also, a  
particular course belongs to only one school.

## Step 1) Identifying Entities.
#### How?
List all named things, nouns.
- Alongside it, list attributes mentioned with it.

School
University
Lecturers
Student
Course
Module

Then filter through this list.
- Combine duplicates and or multiple things with the same meaning into one.

After filtering...

School
Lecturer
Course
Student
Module

## Step 2) Identifying Relationships
Re-read the given example and hunt down relationships / conditions between the stated entities. List them out beneath each.

School
- Has a number of lecturers.
- Offers a variety of courses.
Lecturer
- May teach a number of modules.
- May advise a group of students.
- Employed by only 1 school.
Course
- Has a number of modules.
- Belongs to only 1 school.
Student
- Enrols on course.
Module
- Taught by 1 lecturer.

The names of relationships between entities is the verb in each sentence detailing the relationship.

![[Pasted image 20250705202001.png]]

Now, the types of the relationships must be determined.
- Return to captured sentences, and think...
	1) Does entity A have that association with more than 1 of entity B.
		- IF true, relationship (A,B) is (1:m).
	2) Does entity B have that association with more than 1 of entity A.
		 - IF true, relationship (A, B) is (m:1)
	- IF BOTH TRUE, relationship (A, B) is (m:m).

- To determine if the relationship is either mandatory or optional, think...
	1) MUST each occurrence of entity A have that relationship with at least ONE of entity B?
		- IF true, B is mandatory.
	2) Do same with swapping places (MUST entity B...).

Thus giving a completed ERD
![[Pasted image 20250705202739.png]]
