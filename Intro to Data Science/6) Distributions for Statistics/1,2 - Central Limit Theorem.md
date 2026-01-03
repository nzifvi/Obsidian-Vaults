[[1,1 - Gaussian Distribution]] <- Back

---
# What is the Central Limit Theorem?
Central Limit Theorem, CLT, describes distribution of a sample's mean over n independent


$$
\bar{x} = \frac{1}{|X|}\sum_{i = 1}^{|X|}[x_i]
$$

$$
S = \{\bar{x_1}, \bar{x_2},...,\bar{x_n} \}
$$
$$
\bar{S} = \frac{1}{|S|}\sum_{i=1}^{|S|}[\bar{X_i}]
$$

As $|S| -> \infty$, $\bar{S}$(Mean of sample of means) converges to $E[\bar{X}]$ (expected value of the sample of means.)

$$
E[\bar{X}] = \mu
$$
- $\mu$ is the population mean.
- As the number of samples present in the sample of means increases, the mean of the sample of mean better approximates

A sampling distribution of means, as the number of samples present increases,

$$
z_i = \frac{\bar{x_i} - \mu}{\frac{\sigma}{\sqrt{|S|}}}
$$
- Centres the mean at 0 and scales the variance to 1.

As the size of each sample increases by an equal amount across all samples...
$$
\frac{\bar{x_i - \mu}}{\frac{\sigma}{\sqrt{|X_i|}}} \rightarrow^{d} N(0,1)
$$
- Regardless of the distribution this sample is pulled from, the distribution of the sample mean converges into a Gaussian.

