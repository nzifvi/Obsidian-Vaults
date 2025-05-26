[[2,1) Sample Spaces]] <- Back


---
## Set Theory in Probability
Set theory is very useful in probability. It provides a large amount of notation, and language, for expressing handling sets.

It is important to note that any duplicate elements, that is elements with the same value, are voided: leaving only 1 of n duplicates.
#### 1) Union
Union is the combination of 2 sets

$$A = \{1, 2, 3\}$$
$$B=\{10, 11, 12\}$$
$$A \cup B = \{1, 2, 3, 10, 11, 12\}$$

#### 2) Intersection
Intersection, of 2 sets, produces a set containing ONLY elements that are shared between the 2 sets the intersection was performed on.

$$C=\{100, 12, -1, 8\}$$
$$D = \{200, -2, 5, 9, 15, 100\}$$
$$C\cap D = \{100\}$$

#### Set Complement
The set complement of a set produces a set of all elements that are in some universal set U and NOT in the set the complement is being taken of.

$$A = \{1, 2, 3, 4, 5, 6\}$$
$$U=\{1, 2, 3, 4, 5, 6, 7, 8\}$$
$$A^{C} = \{7, 8\}$$
Set complement can be written in logical notation in order to clearly show how to produce the complement of a set...
$$A^{C} = \{x \mid x\not\in A \wedge x\in U\}$$
In English: element x is not a member of A and x is a member of U. 