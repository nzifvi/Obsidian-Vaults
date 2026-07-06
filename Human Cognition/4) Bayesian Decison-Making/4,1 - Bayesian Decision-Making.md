[[2,4 - Markov Decision Processes]] $\leftarrow$ Back
[[4,2 - Predictive Coding]] $\leftarrow$ Next

---
# Bayesian Decision-Making
## 1D Kalman Filters
Kalman Filters = A Bayesian filter.
- Performs recursive Bayesian estimation.

Goal of a Kalman Filter = estimate an unknown state by updating predictions about uncertain input with prediction errors.
- Kalman Filters learn a generative model.

Kalman filters useful for working with dynamic states which change over time: estimating said states.
## Setting up Kalman Filters
1) Initialise a Gaussian prior.

2) Get a noisy sensory estimate.

3) Predict state
	- Done by weighted sum of prediction & input.

4) Update prior.
	- Estimate mean and variance of input using Kalman gain, $K_k$ & prediction error.

### Kalman Gain
Kalman Gain, $K_k$, is a weighting factor that minimises estimation error.
- Determines how much to trust a new sensor measurement versus the predicted state.

Let...
- $P_k^-$ denote the predicted error covariance.
- $H$ is the observation model.
- $R$ is the measurement

$$
K_k=P_k^-H^T(HP_k^-H^T+R)^{-1}
$$