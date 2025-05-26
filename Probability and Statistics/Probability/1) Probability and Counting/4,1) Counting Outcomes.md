[[3) Naïve Definition of Probability]] <- Back
[[5) Non-Naïve Definition of Probability]] <- Next

---
Calculating naive probability of an event A requires counting number of outcomes in event A's set

AND...

counting number of possible outcomes in the sample space S that event A is derived from.

Sometimes, sets can be extremely large. This section discusses various counting methods to reduce the issue of counting.

### 1) Multiplication Rule
Only applicable when there is a constant value repeatedly present.

$$
c = b+b+...+b
$$
Instead of summing up b again and again...

let a equal the number of times a b term appears...

$$
c = ab
$$


The multiplication rule is incredibly useful for handling probability trees

![[Pasted image 20250414135632.png]]


Suppose you are given a probability tree representing the possible outcomes of a sample space S

$$S = \{A, B, C\}$$
The probability tree models the probability of each possible outcome from 2 rolls. Each roll would be a random variable which is an outcome of the sample space.

$$
X_{1}, X_{2} \in \{A, B, C\}
$$
Suppose we want to solve the naïve probability that both our possible outcomes will be A. Furthermore, suppose EACH possible outcome has an equal probability of occurring.

$$
P_{naive}(X_{1} = A \wedge X_{2} = A)
$$


Using the multiplication rule, and consulting the binary tree plus the Sample Space set...
1) We can determine that we have 3 possible outcomes for the first combination.
2) For each first possible combination, a further 3 possible outcomes follow.

Thus...

$$|S| = 3 *3 = 9$$

Using the multiplication rule, and consulting the probability we want's notation, we need to count each time the condition is true
- Which is just once where the first and second outcome is both equal to A

Thus...


$$
|A_{1}| = 1
$$

So...

$$
P_{naive}(X_{1} = A \wedge X_{2} = A) = \frac{1}{9}
$$

Other questions can be asked, such as...

$$
P_{naive}(X_{1} = A)
$$

Using the same approach...

$$
|S| = 9, |A_{2}| = 3
$$
$$
P_{naive}(X_{1} = A) = \frac{3}{9} = \frac{1}{3}
$$


### 2) 