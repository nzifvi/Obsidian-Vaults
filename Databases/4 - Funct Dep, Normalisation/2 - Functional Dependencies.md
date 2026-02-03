[[1 - Anomalies]] $\leftarrow$ Back
[[3 - Normalisation]] $\leftarrow$ Next

---
# What is a Functional Dependency?
Functional dependency, FD, is a relationship between attributes in an entity.
- Value of 1 attribute, or a set of attributes, will uniquely identify the values of other attributes.
- One output (the attribute that is functionally dependent on the input) can be functionally dependent on multiple inputs (the attribute that the output is functionally dependent on).



If attribute A functionally determines attribute B, this is denoted as:
$$
A \rightarrow (B)
$$

$A \rightarrow (B)$ means that for every unique value of A, a unique value of B exists. 
- That value of B will not occur for any other value of A in a 1:1 relationship.
- In 1:m relationships, one B can occur for multiple As.
- CANNOT HAVE MULTIPLE Bs occurring for a singular A.


![[Pasted image 20260104192212.png]]

$$
\{clientNo, propNo\} \rightarrow (startDate)
$$
- propAddress is not functionally dependent on clientNo, as unique values of clientNo have the same propAddress $(clientNo = 56, propAddress=$ 3 London Rd, Brighton$)$ and $(clientNo = 12, propAddress=$ 3 London Rd, Brighton$)$ 



# Full Functional Dependencies
$$
A \rightarrow B
$$
B is fully functionally dependent on A if and ONLY if B does not functionally depend on any subset of A.

$$
\{clientNo, propNo\} \rightarrow startDate
$$
$$
clientNo \cancel{\rightarrow} startDate \wedge propNo \cancel{\rightarrow} startDate
$$
# Full Dependencies Diagram
Full dependencies diagram is a visual way to represent all functional dependencies within an entity.

In a full dependency diagram...
- Nodes, aka vertices, are attributes of a entity.
- Edges represent that a functional dependency exists between source and target: target is functionally dependent on source.

![[Pasted image 20260104192212.png]]


![[Pasted image 20260104194300.png]]

$$
\{clientNo, propNo\} \rightarrow startDate
$$
$$
startDate \rightarrow (propNo, clientNo)
$$
$$
ownerNo \rightarrow ownerName
$$
$$
\{clientNo, startDate\} \rightarrow (propNo, propAddress, ownerNo, ownerName)
$$
- clientNo, by itself, cannot uniquely identify ownerName. However, $\{clientNo, startDate\}$ as a pair will have unique values that uniquely identify an ownerName.
