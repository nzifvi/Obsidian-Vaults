[[2,1) Sample Spaces]] <- Back
[[4,1) Counting Outcomes]] <- Next

---
## Naïve Definition of Probability
Historically, earliest definition of probability of an event occurring was to count the number of ways the event could happen and then divide that by the number of possible outcomes for the experiment.
- This is the naïve definition of probability.

Why is this the naïve definition of probability?
1) Restrictive.
2) Relies on strong assumptions which, if the assumptions are not actually true, result in an incorrect probability.

$$
P_{naive}(A) = \frac{|A|}{|S|}
$$

The probability that an outcome, from the event set A, does not occur can be found with...

$$
P_{naive}(\neg A) = \frac{ |A^{C}|}{|S|}
$$

Which simplifies to...

$$
P_{naive}(\neg A) = 1 - \frac{|A|}{|S|}
$$

If $P_{naive}(A)$ cannot be found, it might be easier to find $P_{naive}(\neg A)$ might be easier to find.
- From $P_{naive}(\neg A)$, $P_{naive}(A)$ can be found and vice versa.
## Naïve Definition of Probability Limitations

1) S, the set of all possible outcomes, must be finite.

2) It can be misleading. It assumes that each outcome of the event set has an EQUAL chance to occur when this may not be the case.


## Naïve Probability  and it's Consequences
#### 1) Symmetry
If, for an event, all outcomes are equally likely then the outcomes are symmetrical.

The distribution produced by this is referred to as a uniform distribution

Assume all outcomes are equally likely.

Example:

$$
S = {1, 2, 3, 4}
$$

$$
A = {1, 2}
$$

$$
P_{naive}(A = 1 \mid A = 2) = \frac{2}{4}
$$


The distribution of $P_{naive}(A)$ can be visualised as...

```chart
type: bar
labels: [A = 1, A = 2]
series:
	- title: P(A)
	  data: [0.5, 0.5]
```

When all outcomes, of an event A out of a sample space S, are equally likely, you can use the naïve definition of probability for calculations.
- To test, the probability for multiple events, with the same size, must have equal probability for all possible outcomes.


#### 2) Null Model
You can just assume that a sample space's possible outcomes are all of equal probability. This is called a null model.

This is done to just basically see what predictions can be produced 

AND THEN

you can compare the predictions from a null model with predictions from observable, real world data to evaluate the hypothesis if equally probable outcomes are tenable.