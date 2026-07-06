[[3,1 - Reinforcement Learning]] $\leftarrow$ Back
[[3,3 - Policies]] $\leftarrow$ Next

#MDP #DPHC-Models #MarkovModels #ReinforcementLearning

---
# Markov Property
To create markov models, the markov property is invoked.
- ANY markov model operates under the assumption that the markov property is true.

The markov property is...
$$
P(X_{t+1}=x|X_t, X_{t-1},...,X_{t-|T|})=P(X_{t+1}=x|X_{t})
$$
The probably of $X_{t+1}$ having the value of x is ONLY dependent on the value of $X_{t}$

When building markov models, a specific type of Markovian process is used.
- aka markov decision process

The markov decision process states...
$$
P(S_{t+1}=s |S_t,A_t,...,S_{t-|T|},A_{t-|T|})=P(S_{t+1}|S_t,A_t)
$$
- Probability of being in state s at t+1 depends on the state at t and the action made at t.

# Markov Decision Process (MDP) Mathematics
MDPs are defined with a tuple of information
$$
MDP = (S, A, P, R)
$$
Where...
- $S$ is a set of all possible states.
- $A$ is a set of set of actions available in a given state.

$$
A=\{A_{s_1},...,A_{s_{|S|}}\}
$$
- $P_a$ are the transition probabilities between states $s_{t}$ and $s_{t+1}$ after taking action a.
	- There are $|A|$ transition probability vectors. One for each action.
	- The transition vectors form an overall transition probability matrix.

- $R_a$ are the rewards received after transition from state s to state s' after taking action a.
	- Similarly, there are $|A|$ reinforcement vectors. One for each action.
	- The reinforcement vectors from an overall reinforcement matrix
## Transition Probability Matrix
For EACH possible action, there exists a transition probability matrix.


For each action, $a_k$, it's transition probability, $P_{|S|^2}(a_k)$ matrix is equal to...
$$
\mathcal{P}_{|S|^2}(a_k) = \begin{bmatrix}
\mathcal{p}_{1,1}(a_k) &...&\mathcal{p}_{1, |S|}(a_k)\\
\vdots & \ddots & \vdots \\
\mathcal{p}_{|S|, 1}(a_k) &...& \mathcal{p}_{|S|, |S|}(a_k)
\end{bmatrix}
$$
$$
\mathcal{p}_{i,j}(a_k) = P(s_j | s_i, a_k)
$$
- $p_{i, j}(a_k)$ denotes the transition probability of moving from state $i$ to state $j$ after action $a_k$
Where...
- Each row of the transition probability matrix sums to 1.
$$
\forall i, i \leq |S| \quad\sum_{j=1}^{|S|}\biggr[p_{i, j}(a_k)\biggr] = 1
$$
- The diagonal represents the transition probability of remaining in the same state.

## Reward Matrix
For each action, $a_k \in A$, there exists a reward matrix $R_{|S|^2}(a_k)$. This is equal to...
$$
R_{|S|^2}(a_k) = \begin{bmatrix}
r_{1,1}(a_k) &...&r_{1,|S|}(a_k)\\
\vdots&\ddots&\vdots\\
r_{|S|,1}(a_k)&...&r_{|S|, |S|}(a_k)
\end{bmatrix}
$$
- $r_{i, j}(a_k) = \mathcal{R}(s_i, a_k, s_j)$ is the reward for transition from state $s_i$ to state $s_j$ via action $a_k$

### Reward Function
The reward function, $\mathcal{R}$, has 3 variants.
- $\mathcal{R}(s_i)$ is the reward for being in state $i$
- $\mathcal{R}(s, a)$ is the reward for taking a certain action whilst being in a state.
- $\mathcal{R}(s, a, s')$ is the reward for taking an action which transitions you from state $s$ to state $s'$

