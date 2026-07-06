#FaceAlignment
#AML

[[3 - Measuring Error in Face Alignment]] $\leftarrow$ Back

---
# Histograms
Histograms can be used to analyse the count of errors.

# Box Plots
Boxplots can be used to visualise data about the error between two models.
- Good for comparing between 2 models.


# Cumulative Density Function Plots
Cumulative density function, CDF, plots can be used as error analysis for facial feature detection.

The y-axis represents cumulative density.
- Proportion (percentage if multiplied by 100) of samples where the error is less than or equal to a given error magnitude.

The x-axis represents the error magnitude.

$$
CDF(x) = P(\mathcal{L} \leq x)
$$

## Uses
CDF plots allow for...
1) Tolerance analysis.
	- Allows to figure out what percentage of predictions are within x pixels (read y value at x value)
2) Model comparison.
	- Can plot 2 CDFs for 2 models to see how they compare.
	- Can also plot 2 CDFs for how a model performs on a training set versus test set.
		- If line is similar, model has good generalisation.
3) Outlier detection.

4) Performance thresholds
	- Using the inverse of the CDF, you can solve for a minimum error to get y accuracy.
$$
CDF^{-1}(y)=x
$$
## In Python

```python
import numpy
import matplotlib.pyplot as plt

for dataItem in [data1, data2]:
	plt.step(
		numpy.sort(dataItem),
		numpy.linspace(0, 1, len_(dataItem))
	)
plt.show()
```
