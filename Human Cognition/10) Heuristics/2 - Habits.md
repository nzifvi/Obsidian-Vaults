[[1 - Normative Decision-Making]] $\leftarrow$ Back

---
# 

$$
\nabla_{\vec{\theta}}L(\theta_t)
$$
$$
\bar{m}_t = \beta_1 \bar{m}_{t-1} + (1 - \beta_1)\nabla_\vec{\theta}L(\theta_t)
$$
$$
\bar{v}_t = \beta_2 \bar{v}_{t-1}+(1-\beta_2)\nabla_{\vec{\theta}}L(\theta_t)^2
$$


$$
\theta_{t+1} = \theta_t - \bar{m}_t\frac{\eta}{(\sqrt{\bar{v}_t} + \epsilon)}
$$

$$
\lim_{\bar{v}^t \to \infty} \biggr[\frac{\eta}{(\sqrt{\bar{v}_t} + \epsilon)}\biggr] = 0
$$
- As the second momentum, the running mean of gradients, increases, the global learning rate is divided by an increasingly large amount, and the weight update term approaches 0.

$$
\lim_{\bar{m}_t \to \infty} \biggr[\bar{m}_t\frac{\eta}{(\sqrt{\bar{v}_t} + \epsilon)}\biggr] = \infty
$$
- As the first momentum, the running mean of squared gradients, increases, the weight update term increases in momentum.
	- Absolute values of the difference between a new weight update term and old weight update term become larger.
	- Higher momentum = higher inertia: the weight update term is heavily influenced by the momentum.