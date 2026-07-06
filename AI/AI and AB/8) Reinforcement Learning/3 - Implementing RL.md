[[2 - Mathematics of RL]]

---
# 1) Markov Decision Processes
Markov Decision Processes, MDPs, are used to implement RL usually.
- MDPs define the problem/environment.
- RL is the defined method which uses RL to learn how to act in the environment.

RL assumes the environment is an MDP: assuming environment satisfies Markov property.
- Assumes the current state contains all the necessary information.

MDPs can be modelled by.
1) Matrices

## MDP modelled by Matrices
MDPs can be modelled by matrices when...
1) States are finite.
2) Actions are finite.

Let...
- $S$ denote a set of possible states.
- $A$ denote a set of possible actions.

### Transition Matrices
For each action, a, a transition matrix, $P(a)_{|S|^2}$, will be defined
$$
P(a)_{|S|^2}=\begin{bmatrix}p_{1,1}&...&p_{1,|S|}\\...\\p_{|S|,1}&...&p_{|S|,|S|}\end{bmatrix}
$$
$$
p_{i,j}\in P(a)_{|S|^2}
$$
$p_{i,j}$ denotes...
$$
p_{i,j}=P(s_j|s_i,a)
$$
- probability of going from state $i$ to state $j$ when taking action a.

### Reward Representation
Two common ways of representing rewards:
1) Reward Matrix
2) Reward Vectors

#### Reward Matrix
A reward matrix, $R$, represents all possible rewards.
$$
R_{|S|\times|A|}=\begin{bmatrix}r_{1,1}&...&r_{1,|A|}\\...\\r_{|S|,1}&...&r_{|S|,|A|}\end{bmatrix}
$$
$$
r_{i,j}=r(s_i,j)
$$
- $j \in A$
- $s_i \in S$

#### Reward Vectors
Reward vectors approach results in there being a reward vector per action.
$$
\vec{r}(a)_{|S|\times1} = \begin{bmatrix}r_1\\...\\r_{|S|}\end{bmatrix}
$$
$$
r_{i} \in \vec{r}(a)_{|S|\times1} \Rightarrow r_{i}=r(s_i, a)
$$
### Value Function Representation
The value function is represented as a vector for all possible states.

$$
\vec{v}_{|S|\times1}=\begin{bmatrix}v_1\\...\\v_{|S|}\end{bmatrix}
$$
$$
v_i\in \vec{v}_{|S|\times1} \Rightarrow v_i = v(s_i)
$$
