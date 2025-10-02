[[2) Types of Graphs with Matplotlib]] <- Next

---
## Plotting Graphs with Matplotlib
Any graph, (line, bar, etc), has the same structure for it to be created in Matplotlib

```python
# get data (define or pass to a function which returns a plot)

# vvv

# load data into the plot and specify what type of graph the plot is (line, bar chart, etc).

# customise the plot

# return, or show(), the plot.
```


```python
import matplotlib.pyplot as plot1;

def getLineGraph(zippedData):
	xValues, yValues = zip(*zippedData) # data is prepared for loading.
	plot1.plot(xValues, yValues) # data is loaded
	return plot1 # return the plot for further customisation

xOrdinates = [1, 2, 3]
yOrdinates = [4, 8, 12]

plot1 = getLineGraph(list(zip(xOrdinates, yOrdinates)))
plot1.show()
```

.plot() calls a specific constructor and assigns it to the object known as plot1.
- It is a specific type of class, known as Plot. 
- Multiple types of graphs can be constructed via a set of constructors.
- Each constructor has a minimum set of arguments that must be passed.

.show() is used to load the graph in a separate GUI. Before this is called, ALL modifications must be made to the graph.