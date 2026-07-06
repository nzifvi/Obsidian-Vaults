[[3,2 - Markov Models]] $\leftarrow$ Back
[[3,4 - RL Functions]]      $\leftarrow$ Next

#ReinforcementLearning 

---
# 1) What are Policies?
A policy is a strategy that agents use to select actions.
- Defines agent's behaviour by mapping states to actions.
OR
- Defines agent's behaviour by mapping probability distributions over actions.

SIMPLE DEFINITION: A policy, $\pi$, is a function that species what action to take in each state s.

Two types of policies exist.
1) Deterministic Policy 
2) Stochastic Policy

## 1.1) Deterministic Policy
A deterministic policy maps each state to a single specific action
$$
\pi : S \rightarrow A
$$
- The policy outputs a unique action for each and every state.
$$
\pi(s) = a
$$
## 1.2) Stochastic Policy
A stochastic policy maps each state to a probability distribution over actions.
$$
\pi : S \times A \rightarrow [0, 1]
$$
- $\pi(a|s)$ is the probability of taking action a in state s.

Some constraints exist, due to stochastic policies being probabilistic 
$$\forall s\in S, \forall a\in A \quad\quad\pi(a|s) \geq 0$$

$$
\forall s\in S \quad\quad\sum_{a\in A}\bigg[
\pi(a|s)
\bigg] = 1
$$
- The probability sums to 1, obeying probability axioms.

Every deterministic policy is a special case of stochastic policy where...
- For one action, $a_{j}$, $\pi(a_j | s) = 1$ 
- $\forall a, a\in A-\{a_j\} \quad \pi(a|s) = 0$ (all other actions have a probability of 0 of occurring)

# 2) Optimal Policies
An optimal policy, $\pi_{optimal}$, is desired to...
- Determine which action to choose at which state.
- Be stable over time.
- Fully describe behaviour (choices made)

Optimal policies must be learned. This is achieved by finding the policy that maximises getting into states with the largest, long term expected reward