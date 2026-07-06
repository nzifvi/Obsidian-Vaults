[[2,3 - Tree Search]] $\leftarrow$ Back

---
# What is A Markov Decision Process (MDP)
Markov Decision Processes, MDPs, are a powerful way to model multistep decisions in uncertain environments.
- Can handle all types of uncertainty.
- MDPs = basis of reinforcement learning.

MDPs are Markovian.
- Markovian is a stochastic process. Future states can ONLY be predicted from current states. It has no memory of past states.

![[Pasted image 20260304103237.png]]

An MDP will have...
- An Agent.
- An Environment $E$

At time t... Agent makes action $A_t$ in environment $E$
- Action $A_t$ makes puts agent into some sort of state $S_t$. 
- A reward, $r_t$, is associated with the action made 

# Mathematics for MDPs
A Markov Decision Process, $M$, is described as a 4 tuple:
$$
M=(S, A, P_{a'}, R)
$$
Where...
- $S$ is the state space (set of all possible states.)
$$
S=\{s_1,...s_{|S|}\}
$$
- $A_{s_i}$ is the action space (a set of all actions for each state s).
	- An action space EXISTS per state s.
$$
A_{s_{i}}=\{\}
$$
- $P_{|S|^2}$ is the transition matrix:
	- Probability of getting from $state$ to $state'$.
$$
P(state, state')\in P
$$


- $R$ is the reward space (set of all rewards for an action space)
	- EACH action space has a corresponding reward space.

# MDP Example
Let K denote knowledge.
- Knowledge has three possible states: High, Medium, Low
$$
S=\{K_H, K_M, K_L\}
$$
$$
A_{K_H}=\{Revise, Break\}
$$
$$
A_{K_M} = \{Revise, Break\}
$$
$$
A_{K_L} = \{Revise, Break\}
$$



|       | $K_H$         | $K_M$         | $K_L$         |
| ----- | ------------- | ------------- | ------------- |
| $K_H$ | $P(K_H, K_H)$ | $P(K_H, K_M)$ | $P(K_H, K_L)$ |
| $K_M$ | $P(K_M, K_H)$ | $P(K_M, K_M)$ | $P(K_M, K_L)$ |
| $K_L$ | $P(K_L, K_H)$ | $P(K_L, K_M)$ | $P(K_L, K_L)$ |

# Optimal Policies
For a sequence of states that have been taken, the total payoff for the sequence of states is...
$$
s_{taken}=<s_0,,...,s_n>
$$
$$
\sum_{i=0}^{n}\biggr[\gamma^{i}R(s_i)\biggr]
$$
A policy is denoted by $\pi$

The value of $i^{th}$ policy, $\pi_i$ is equal to...
$$
V_{\pi_i}(s_{taken})=E\biggr[\sum_{i=0}^n\biggr[\gamma^{i}R(s_i)\biggr]\biggr]
$$
The most optimal policy, can be solved using the Bellman equation:
$$
V^{*}(s)=R(s)+\max_{a\in A}\biggr(\gamma\sum_{s'}\biggr[P(s'|s,a)V(s')\biggr ]\biggr)
$$