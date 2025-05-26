[[4,1) Counting Outcomes]] <- Back

---
## Combinatorics
Combinatorics = field of mathematics which studies how, and how many ways, a thing can be counted.

Combinatorics has many applications:
- Probability/Statistics.
- Physics.
- Graph Theory.
- Cryptography.
- Computer Science.


## 1) Factorials
Factorials allow for the number of orders in which something can happen to be solved.

Example:
	In a class, there are 4 chairs and 4 students standing in a row. How many possible orders, aka combinations, can the students sit in the 4 chairs?


![[Pasted image 20250419170521.png]]

Until a student sits down, there are 4 possible places the student can sit.
- Student 1 sits down, a chair is occupied.
- For the remaining students, there are now 3 possible spaces.
- This continues until all positions are exhausted.

$$
4 \times3\times2\times1 = 24
$$

Therefore there are 24 possible orders the 4 students can sit in the 4 chairs.

This can be expressed as a factorial:

$$
n! = n \times(n-1)\times(n-2)\times...\times1
$$
Where n is the possible positions.

The factorial, of n, $n!$ produces the total possible orders something can be in.

## 2) Permutations
Suppose that you have k possible positions
![[Pasted image 20250419171206.png]]
However, you have n objects and those n objects do not have enough possible positions, k, to all have a position.

That is a permutation problem.

A permutation problem can be used to solve:
"How many different possible orders are there for any n objects, or events, to be arranged out of k positions"

There are 2 possible positions, k = 2.
There are 4 objects or events, n = 4.

Therefore, the different possible orderings of n objects out of k possible positions is equal to...

$$
^nP_k = \frac{n!}{(n-k)!}
$$

So, solving the problem in this case...

$$
^{4}P_{2} = \frac{4!}{(4-2)!} = \frac{4 \times 3 \times 2 \times 1}{2 \times 1} = 12
$$
Therefore, there are 12 possible orders 4 students can sit on 2 positions.

NOTE: 
Permutations are used when the order that objects, or events, can be in.
- It assumes that no n objects, or events, can occupy the same space order. They always have to be in a different space.

\_ _  { 2 positions
\1 2 3 4 { 4 objects OR events

1 2 -> 1
2 1 -> 2
3 1 -> 3
1 3 -> 4
2 3 - > 5
3 2 - > 6

1 4 -> 7
4 1 -> 8
2 4 -> 9
4 2 - > 10
3 4 -> 11
4 3 -> 12

Thus, 12 possible permutations
- Note, there is not one permutation where one of the objects, or events, occupies multiple spaces. Once an object, or event, is put into a position: it cannot be used elsewhere in the permutation.

Examples of permutation problems
- 5 ingredients, only 3 can be selected.
- 2 day, 3 types of weather can occur and the next day's weather is NOT the previous day's weather.

Output permutation gives:
- How many unique orderings can I have of n objects in k places.

## 3) Combinations
Combinations solve the problem of
	Regardless of order, how many k objects can be chosen from n total objects, or positions.

With combinations, the same object can remain in the same position.

Suppose we have 6 ingredients, but only 3 can be selected, what are the total number of combinations of 3 ingredients can I have?
Let n = the total number of objects, or positions.
Let k = the amount of objects, or positions, you can have.

$$
^{n}C_{k} = \frac{n!}{k!(n-k)!}
$$

So... to answer the question...

$$
^{6}C_{3}=\frac{6!}{3!(6-3)!} = 20
$$

Therefore, there are 20 possible combinations 3 out of 6 ingredients that can be selected 