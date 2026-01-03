Using the logical schema produced, such as...

```
Staff(__staffNo__, firstName, lastName, branchNo)
primary key staffNo
foreign key branchNo references Branch(branchNo)
branchNo not null

Branch(__branchNo__, address)
primary key branchNo
```

A diagram can be produced.

![[Pasted image 20251229201125.png]]