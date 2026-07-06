[[3,3 - Policies]]                   $\leftarrow$ Back
[[3,5 - Temporal Learning]] $\leftarrow$ Next

#ReinforcementLearning

---
# Important Variables
## 1) Discount Factor
The discount factor, $\gamma$, is a hyperparameter which controls how much an agent, using RL, prioritises future rewards over immediate rewards.

A reward is discounted so that rewards further in the future carry smaller weight.
$$
\gamma \in [0, 1]
$$
- As $\gamma \rightarrow 1$, agent increasingly prioritises future rewards.
- As $\gamma \rightarrow 0$, agent increasingly prioritises immediate rewards.
	- Aka making agent myopic.

Future rewards are discounted so that rewards further in the future carry smaller weight. This is done because.
1) Makes RL more realistic because the future is more uncertain.
2) Doing so is mathematically convenient.
3) Humans and animals prefer immediate rewards so discounting future rewards is realistic.
# 1) Return
The return function is the sum of discounted reward from time t.
$$
G_t = \sum_{k=0}^{\infty}\biggr[
\gamma^kR_{t+k+1}
\biggr]
$$
$$
G_t = \gamma^0R_{t+1} + \gamma R_{t+2} + ...
$$
$$
\gamma R_{t+2}+... = \sum_{i=1}^{\infty}\bigg[\gamma^k R_{t+k+1} 

\bigg] = G_{t+1}
$$
There is a recursive formulation of the return...
$$
G_t = \gamma^0R_{t+1} + \gamma G_{t+1}
$$
- The recursive formulation is vital to how the Bellman equations work.


There is a finite horizon formulation.
- Episodic tasks with a terminal time T.
$$
G_t = \sum_{k=0}^{T-t-1}\bigg[
\gamma^{k}R_{t+k+1}
\bigg]
$$

There is an expected return under a given policy $\pi$
$$
V^{\pi}(s) =\mathbb{E}_\pi[
G_t | S_t = s
]
$$
# 2) Policy Value Function
The policy value function, $V^{\pi}(s)$, is the expected reward from state s under policy $\pi$.
$$
V^{\pi} : S \rightarrow \mathbb{R}
$$
$$
V^{\pi}(s)=\mathbb{E}_{\pi}\biggr[G_t | S_t = s\biggr]
$$
The value of a policy $\pi$ is the expected total time-discounted reward that is received by following that policy from $s_0$
