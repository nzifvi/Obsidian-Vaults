[[2 - Overfitting and Underfitting]] <- Next

---
# 1) What is Bias and Variance
Bias and variance are important metrics for ensuring ML models perform well on new, unseen data.

Bias and Variance explain why...
1) Models may generalise well.
2) Models may underfit.
3) Models may overfit.

# 2) Bias
Bias is the error that occurs when an ML model is too simple to recognise true patterns in given inputs.
- High Bias = model oversimplifies, misses patterns in input and UNDERFITS data.
- Low Bias = model captures patterns well and is closer to the true values.

## 2.1) Calculating Model Bias
$$
Bias(x)^2 = (E[g(x;\vec{\theta})] - f(x))^2
$$
- $g(x;\vec{\theta})$ is the approximating function at value $x$.
- $f(x)$ is the objective function at value $x$.
- $E[g(x;\vec{\theta})$ is the expected value of the approximating function.
# 3) Variance
Variance is how much a model's predictions change when it is trained on new, different data.
- High Variance = model is too sensitive to small changes in data and may overfit: recognising patterns when there is nothing there.
- Low Variance = model is more stable but may miss some patterns.
	- As variance decreases, model becomes increasingly less sensitive to changes in data.

Variance comes from insufficient data.
- To reduce variance, model must be trained on more data.

## 3.1) Calculating Model Variance
$$
Var(x)=E\biggr[(g(x;\vec{\theta})-E[g(x;\vec{\theta}])^2\biggr]
$$
- $E[g(x;\vec{\theta})$ is the expected value of the approximating function.
- $g(x;\vec{\theta})$ is the approximating function at value $x$.

## 3.2) Reducing Variance
A model's variance can be reduced by...
1) Simplifying the Model:
2) Increase the amount of training data:
	- To reduce variance, model can sometimes be trained on more data.
3) Use regularisation:

# 4) Bias-Variance Trade off
A moderate amount of bias and variance is often desired in a model, as it achieves the best generalisation when a model encountering new, unseen data.

| Model Type   | Bias     | Variance | Result                                                                                                                                                                                                       |
| ------------ | -------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Underfitting | High     | Low      | Poor training and test performance.<br>- High bias causes model to not recognise patterns.<br>- Low variance causes model to be less sensitive to changes in training data: missing patterns.                |
| Optimal      | Moderate | Moderate | Best generalisation.<br>- Moderate amount of bias means patterns are somewhat recognised in input data.<br>- Moderate amount of variance means that model's predictions are responsive to new training data. |
| Overfitting  | Low      | High     | Poor test performance.<br>- Model is good at recognising patterns in given input data.<br>- High variance causes model to be too sensitive: predictions become unstable.                                     |


