
---
## What is Conditional Probability?
Whenever new evidence is observed, such as getting data, the degree of certainty / uncertainty about something may change.
- This is how humans think.

Suppose you are about to invest into a stock you feel confident about.
- You then read that the company you are about to invest in lost 10 billion last year.
- You would be less confident in your investment, thus less likely to invest potentially.

Suppose you date somebody. You are confident they will not cheat.
- You then learn, in their prior relationship, they cheated (new evidence observed).
- You would be more uncertain about them not cheating on you (degree of uncertainty changed).

Conditional probability is another branch of probability.
- Focuses on the probability of event A given a knowledge of if event B has/has not occurred.

## Bayes Theorem
Bayes Theorem is the implementation of solving the probability of event A occurring given a knowledge of if event B has/has not occurred.

$$
P(A | B) \cdot P(B) = P(B|A) \cdot P(A)
$$

$P(A|B)$ is a conditional. It is the probability of event A occurring given a knowledge of if event B has/has not occurred.

$P(B)$ is the prior. It is the probability of if event B has/has not happened.
- Event B can have multiple possible outcomes.
- So can event A.

Bayes Theorem can be rearranged to solve for specific conditionals...
- Suppose $P(A|B)$ is wanted to be solved for...

$$
\frac{P(A | B) \cdot \cancel{P(B)}}{\cancel{P(B)}} = \frac{P(B|A) \cdot P(A)}{P(B)}
$$
$$
P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}
$$
