[[1 - What is Normalisation]] <- Back

---
## 0NF
In 0NF, no transformation has occurred and will occur in this stage. All that is done is that some document, or example, is adapted into another form to begin normalisation.

![[Pasted image 20250706180822.png]]
The attributes of the above document are put into 0NF: a column of the attribute names.

![[Pasted image 20250706180916.png]]
## 1NF
In 1NF, two things occur.

- The attributes after any non-repeating data are separated into a new entity.
- Any non-atomic data is split into two new attributes.
	- e.g: name into firstName and lastName

The two separated entities in this case will keep a foreign key of the other entity.

![[Pasted image 20250706180822.png]]

- classCode doesn't repeat.
- studentID doesn't repeat.

![[Pasted image 20250706181640.png]]

A PK is denoted in bold.
A FK is denoted with a * appended to it.
## 2NF
In 2NF, any part-key dependencies are split into a new entity.
- ANY entity only has one primary key, and no composite key, then that entity is in 2NF already.
- An entity with a composite key is in an m:m relationship. It must be resolved.

![[Pasted image 20250706211415.png]]

## 3NF
In 3NF, attributes not dependent on an entity's primary key will be split into a new entity.
- This is because all of these attributes, not dependent on an entity's primary key, will be dependent on another attribute.
- That attribute becomes the primary key.

![[Pasted image 20250706211719.png]]