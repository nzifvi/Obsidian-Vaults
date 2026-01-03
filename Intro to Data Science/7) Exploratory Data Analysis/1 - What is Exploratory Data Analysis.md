[[2 - Dangers of EDA]] <- Next

---
# Defining Exploratory Data Analysis
Exploratory Data Analysis, EDA, is a part of statistics used to.
1) Look for hypotheses.
2) Generate questions about a dataset.
3) Perform basic statistical tests on data.
4) Help to uncover any problems with data.

EDA is about pulling interesting questions and hypotheses from a sample.
- Looks for interesting patterns, exceptions, anomalies, or something which is weird about the data set.
- No hypotheses is had before EDA, EDA is a process to produce them.
- You EXPLORE a data set, looking for hypotheses and questions.

EDA does not require any knowledge about how the data is generated or any subject knowledge. It is all about analysing the data itself.
- Dangerous: hypotheses can be found which may not actually be happening, due to subject knowledge.

EDA has four Rs. The Rs are 4 rules to follow in order to perform EDA on a sample.
### 1) Revelation
See the data graphically. Plot it.

### 2) Residuals
Patterns are important to identify. However, it is also important to identify deviations from an identified pattern.
- Is the deviation between sample minus line of best fit.
### 3) Resistance
Any summary statistic (mean, variance, etc) formed from a sample should be resistant to outliers in the sample. 
- Outliers should be checked for and handled appropriately.
- If line of best fit, or summary statistic, changes massively based on an outlier, the sample needs more resistance.
### 4) Re-expression
Sometimes, changing the scales of the axes when graphing data allows for patterns to be identified.
- Using a logarithmic scale, rather than a constant linear scale can help to identify patterns.

![[Pasted image 20251020101557.png]] y-axis uses a constant linear scale here.
- Increases by 5.
- Increases are constant, the difference between points is absolute.
- Distance is the absolute value of the difference between 2 points.

![[Pasted image 20251020101822.png]]y-axis now uses a logarithmic scale.
- Increases in multiples of 10 (1 -> 10 -> 100, etc).
- Increases are relative, each increase becomes a multiple of the prior.
- Distance is relative, has to account for multiplication.

Using a logarithmic scale makes visually identifying linear patterns easier.
- When both axes are logarithmic, everything tends to look as if it has a linear relationship. Can be misleading.
	- Hides potentially massive differences.
	- Usually done by people to hide something big in the sample: misleading or tricking people.