[[2 - Forward Problem vs Inverse Problem]] $\leftarrow$ Back
[[3,2 - Bayes-optimal Integration]] $\leftarrow$ Next

---
# Components of Bayesian Rule
![[Pasted image 20260310181009.png]]
$$
P(B)=P(B|\neg A)P(\neg A)+P(B|A)P(A)
$$

The posterior is proportional to the likelihood times the prior.
- Posterior is AKA conditional probability ($P(A|B)$ in this case).

# Bayesian Updating
Bayesian updating is a statistical method to update the probability of a hypothesis, modelled by the posterior, as more evidence/info becomes available.

Bayesian updating starts with...
1) Prior.
	- Starting assumptions: what is believed before seeing data.
2) Likelihood.
	- New data.
3) Posterior
	- Updated belief after seeing new data.

The updating occurs after calculating the posterior.
- The prior is updated with values of the posterior: influencing the beliefs for any next occurrence of the same type of situation.
- Done by marginalisation.

Per calculation of a prior, you let...
$$
P(A=a|B=b)=\frac{P(B=b|A=a)P(A=a)}{P(B=b)}
$$
Then you update the specific outcome of the prior...
$$
P(A=a)'=P(A=a|B=b)
$$
- Must also update $P(A\cancel{=}a)$
$$
P(A\cancel{=}a)=1-P(A=a)'
$$
... which updates the prior for future reference based on evidence that was encountered.