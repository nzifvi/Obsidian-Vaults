[[1) Plotting Graphs with Matplotlib]] <- Back
[[3) Customising Graphs with Matplotlib]] <- Next

---
## Types of Graphs with Matplotlib

#### 1) Line Plot
Line Plots used to show trends, or continuous data, over time.
- Can also be used to represent functions.

use .plot(x, y) constructor where...
- x is a list of x ordinates.
- y is a list of y ordinates.
- corresponding indices form the coordinates: (x[0], y[0])


#### 2) Scatter Plot
Scatter plots are good for visualising correlations in 2 data sets.

use .scatter(x, y) where...
- x is a list of data.
- y is a list of data.
- each data point is a 2-tuple representing (x[i], y[i])

#### 4) Bar Plot
Bar plots are typically used to compare the number, or quantity, of multiple categories.
- no. of fruits bought.
- etc.

Also used to model discrete probability distributions!
- bar = outcome of a random variable
- height of a bar = P(X = that outcome)

use .bar(categories, values) where...
- categories is a list of categories (each bar is 1 category from this list.)
- values is a list of integers, or floats (each element of this list represents the height of each bar)
- each bar, categories[i], has a height = values[i]


#### 5) Histogram
Histograms are used to show distributions of numerical data
- x-axis represents ranges/bins (age groups, possible outcomes of a random variable, etc).
- y-axis represents frequency (how many values fall into each bin).

Histograms are also good for representing continuous probability distributions, such as the normal distribution.

use .hist(data, len(data)) where...
- data = the values to assign per bin. Each index = a value per bin.
- len(data) where the length is the number of bins to create.

A third argument, density, allows the histogram to be turned into a normal distribution modelling probably density...

use .hist(data, len(data), density=True) to create a normal distribution based around data list.

#### 6) Heatmap
A heatmap is a way of representing a 2D data set, like a matrix, where each matrix element is assigned a colour based on it's value.

Heatmaps are useful for...
1) Correlation matrices.
2) Confusion matrices (machine learning).
3) Matrices of specific values (temperatures).

Allows a matrix and it's values to be visualised.

use .imshow(data, cmap) where...
- data is a 2d list where each element in itself is another list containing values.
- Each element MUST have an equivalent length otherwise the 2d list cannot be represented as a matrix.
	- Fill up all others with a value representing null if one element needs an extra element than all the others.

![[Pasted image 20250421214152.png]]
- cmap sets the colour used by the heat map. Options are:
	1) 'viridis'
	2) 'plasma' (very good one)
	3) 'hot'
		...
#### 7) Error Bars
Error bars are useful when visualising uncertainty, variance, or measurement error in a data set.

Error bars show a range of values above and or below a data point that indicates a possible error.

![[Pasted image 20250421214721.png]]

Upper line represents upper of value the data point can take on (mid + error), bottom line represents a lower bound of value the data point can take on (mid - error).

use .errorbar(x, y, z) where...
- x is a list of x ordinates, setting the x position of each data point.
- y is a list of y ordinates, setting the y position of each data point.
- yerr is a list of errors for each and every data point (the variability in value for EACH data point)
- each data point is defined as a 3-tuple (x[i], y[i], yerr[i])

#### 9) 3D Plots
To use 3D plots with matlibplot, you must...
```python
from mpl_toolkits.mplot3d import Axes3D
```

import Axes3D

use ax.plot3D(x, y, z) where....
- x is a list of x-ordinates.
- y is a list of y-ordinates.
- z is a list of z-ordinates.
- Each point in the plot is a 3-tuple representing a x,z,y coordinate.
- Matching indices from each list form the coordinate: (x[i], y[i], z[i])

