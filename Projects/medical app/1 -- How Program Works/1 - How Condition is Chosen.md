
---
For all roles, there are a set number of conditions they will realistically encounter/be responsible for.
- These conditions are what EACH role will be limited to.


Condition patient has is based on the role and the department that role works in.

How to do this for program:
- Store roles in department.
- Per department, each role is a file which stores conditions they will encounter...

for example...

.../Departments/ER/SeniorDoctor/

could contain...
- broken leg.
- car crash.
- man fell unconscious.
- dangerously high heart bpm.
etc...

Benefits of approach:
- Easy to add more conditions for specific roles in specific departments.
- Easy to implement.

Issues with this approach:
- Duplication. Multiple roles in a department may face the same condition, each role file would have to have a copy of a given condition for them both to encounter it.
	- Leads to larger file size.