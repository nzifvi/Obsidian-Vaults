
---
# What is the Hebbian Rule?
Suppose a pre-synaptic neuron $j$ and a post-synaptic neuron $i$ exist.

The Hebbian rule states: if neuron $j$ spiking causes neuron $i$ to spike: correlating their spiking.
- Correlated spiking results in the synapse between the neurons becoming reinforced.
- Synaptic weight increases.


The discrete mathematical model for the Hebbian rule is...
$$
w_{i,j}(t+1) = w_{i, j}(t)+\eta(r_i\cdot r_j)
$$
...where:
- $\eta$ is the learning rate.
- $r_i$ is the average spiking rate of neuron i.
- $r_j$ is the average spiking rate of neuron j.

When $\eta$ > 0, the synaptic weight is modified depending on if the firing rates of both neurons are non-zero.
- If both firing rates are positive, the weight increases (LTP)
- If firing rate is 0, weight doesn't decrease.
- If one firing rate is positive, the other is negative, the weight decreases (LTD-like)
- If both rates negative, the weight increases


# Statistical Aspect of Hebbian Rule
Averaged over many timesteps, expected difference in weight is proportional to the mean product of firing rates

$$
\langle \Delta w_{i, j} \rangle = \eta \langle r_i \cdot r_j\rangle
$$
- $\langle r_i \cdot r_j \rangle$ is the correlation between the 2 neuron's firing activity.
	- Synapses become reinforced due to pre-and-postsynaptic neurons correlated firing.
	- Can be rewritten as an input correlation matrix $C_{i, j}$
- Hebbian rule accumulates pairwise correlations into synaptic weight using this.


For N presynaptic neurons connecting to neuron i, firing rate of neuron i is determined by...
$$
r_i = \sum_{k=1}^N w_{i, k} r_k
$$
$$
\langle \Delta w_{i, j}\rangle = \eta \bigg(\sum_{k=1}^N\biggr[w_{i, k} r_k\biggr]\cdot r_j\bigg)
$$
$$
r_j \sum_{k=1}^{N}\bigg[w_{i, k}r_k\bigg] = r_j(w_{i,1}r_1 + w_{i,2}r_2+...+w_{1,N}r_N)
$$
$$
r_j(w_{i,1}r_1 + w_{i,2}r_2+...+w_{1,N}r_N) = r_jw_{i,1}r_1+...r_jw_{i,N}r_N
$$
- Re-express summation with $r_j$ coefficient included
$$
\langle\Delta w_{i, j} \rangle = \eta(\sum_{k=1}^{N}\biggr[r_jw_{1,k}r_k\biggr])
$$
$$
\langle r_j \cdot r_k \rangle = C_{j, k}
$$
$$
\langle \Delta w_{i, j} \rangle = \eta \bigg(\sum_{k=1}^{N}\bigg[w_{i, k} C_{j, k}\bigg] \bigg)
$$

Rewrite the summation of synaptic weights as a weight vector of weights onto neuron i...
$$
\frac{dW_i(C)}{dt}=\eta \vec{w_i} C
$$
- Transforms into a linear, differential equation dependent on the correlation matrix C as input.

Correlation matrix, $C$, is symmetric positive semi-definite.
- Has no real non-negative eigen values.
$$
\lambda_1 \geq \lambda_2 \geq ... \geq \lambda_N \geq 0
$$
- Each eigen value, $\lambda_i$, has a corresponding eigen vector $\vec{u}_i$
	- Eigenvector $\vec{u}_1$ is associated with the largest eigenvalue $\lambda_1$.
	- Therefore, $\vec{u_1}$ is the first principal component in the input distribution: direction of GREATEST variance in data.

Decomposing weight vector in the Eigenbasis...
$$
W_i(t)=\sum_{k=1}^{N}\bigg[c_k(t)\vec{u}_k\bigg]
$$
$$
\sum_{k=1}^{N}\bigg[c_k(t)\vec{u}_k\bigg] = c_1(t) \vec{u}_1 + ... + c_N(t)\vec{u}_N
$$
Each correlation coefficient $c_k(t)$ evolves independently as it is a function of time
$$
c_k(t) = c_k(0)e^{\eta\lambda_kt}
$$

The coefficient, with the largest eigenvalue $\lambda_1$, grows fastest. 
- The ENTIRE weight vector becomes aligned with the eigenvector associated with $\lambda_1$ as time passes

>as $t \rightarrow \infty, \frac{\vec{w_i(t)}}{||\vec{w_i}(t)||} \rightarrow \pm \vec{u}_1$  

Therefore, Hebbian rule performs unsupervised PCA.
- Extracts dominant statistical structure from input of stimulus to neurons.