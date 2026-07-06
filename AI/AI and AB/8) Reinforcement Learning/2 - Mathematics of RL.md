[[1 - What is Reinforcement Learning]] $\leftarrow$ Back

---
# Components of RL
- Let $S_{current}$ denote the current state of an agent.
- Let $a_{current}$ denote the current action made by the agent.

A transfer function, $\delta$, maps the agent to a new state given...
- The current state.
- An action that is taken.

$$
\delta(s_{current}, a)=s'
$$

A reward function r, gives a reward for a given state and action taken.
$$
r(s,a)\in R
$$

A policy function, $\pi$, determines what action to take given the state the agent is in.
$$
\pi(s)=a
$$

A value function, $Q$, which is the value of taking action a from state IF agent acts optimally in the next future states.
- Assumes that agent will act optimally from there on.

$$
Q(s,a)\approx Q_{value}
$$

# Q-Learning

## Q-Function
The Q-Function, $Q$, is how RL is performed.
$$
Q(s,a)
$$
- Means "how good is it to take action a in state s"

The Q-Function estimates:
- Immediate reward for taking action a.
- Best possible future reward from taking action a.

$$
Q(s,a)=r(s,a)+\gamma \max\limits_{b\in A}\biggr(Q(s', b)\biggr)
$$
...where...
$$
\max\limits_{b\in A}\biggr(Q(s', b)\biggr) = max\biggr(Q(s', a_1),..., Q(s', a_n)\biggr)
$$


## Discount Factor
The discount factor is to control the importance of future rewards.
$$
\gamma\in [0, 1]
$$
As...
- $\gamma \rightarrow 0$, immediate rewards are prioritised whilst future rewards are less prioritised.
- $\gamma \rightarrow 1$, future rewards are prioritised whilst immediate rewards are less prioritised.

## Determining Best Actions to take from State
Q-Function can be used to figure out best action to take whilst in a given state.
$$
a_{optimal}= \arg\max\limits_{a \in A}\biggr(Q(s,a)\biggr)
$$
$$
\arg\max\limits_{a\in A}\biggr(Q(s,a)\biggr)=\arg\max\limits_{a\in A}\biggr(Q(s,a_1),...,Q(s,a_n)\biggr)
$$
Then, to determine the next state from the optimal action, use the transfer function
$$
s' = \delta(s, a_{optimal})
$$
