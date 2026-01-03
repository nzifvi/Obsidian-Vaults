
---
# What is Instance and Instance Space?
An instance represents an object of interest. Data is a set of instances.
- The set of all possible instances, a sample, is referred to as the instance space.
	- set of all email messages written in english.
	- set of all human faces.

$X$ denotes the instance space.
- Instance is denoted by $x$
- $x \in X$

# What are Labels and Label Space?
In supervised problems, each instance is associated with a label.
- Set of all labels for a task called label space.
	- Class labels $C$ in classification tasks can be for example $C = \{frogs, badgers, ...\}$

Label space denoted by $Y$

Labelling function $f : X \rightarrow Y$ maps instance space to label space.
- Label of a given instance denoted as $f(x)$
- $f(x)\in Y$


For N data points, each with D dimensions (no. of features)...
- X will be a matrix X$[N, D]$ 
- Y will be a vector with shape $[N, 1]$

