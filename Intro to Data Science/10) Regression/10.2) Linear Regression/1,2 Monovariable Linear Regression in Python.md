[[1,1 - What is Monovariable Linear Regression]]

---

```python
import random
import matplotlib.pyplot as plt
import pandas
import time

def generatePatternedSeries(sampleSize:int) -> pandas.Series:
	elements = []
	randomGradient = random.uniform(-10.0, 10.0)
	randomRoot = random.uniform(-10.0, 10.0)
	for i in range(0, sampleSize):
		noise = random.uniform(-20, 20)
		y = (randomGradient*i) + randomRoot + noise
		elements.append(y)
	return pandas.Series(elements)
	

class LinearRegressor:
	def __init__(self, trainingData : pandas.Series):
		self.trainingData = trainingData
		self.weights = [1.0, 1.0]
	
	def approximatingFunction(self, x:int) -> int:
		return self.weights[0]*x + self.weights[1]
	
	def calculateError(self, x:int) -> float:
		residual = self.approximatingFunction(x) - self.trainingData[x]
		return residual**2
		
	def calculateResidual(self, x:int) -> float:
		return self.approximatingFunction(x) - self.trainingData[x]
	
	def calculateGlobalError(self) -> float:
		lossSum = 0
		for i in range(len(self.trainingData)):
			lossSum += self.calculateError(i)
		return (1/len(self.trainingData))*lossSum
		
	def train(self, epochs:int, learningRate: float, tolerance : float = 1e-6):
		sampleSize = len(self.trainingData)
		lastEpochGlobalError = float('inf')
		
		# graph shit
		plt.ion()
		fig, ax = plt.subplots()
		xVals = list(range(sampleSize))
		ax.scatter(xVals, self.trainingData, color='blue', label = 'series')
		line, = ax.plot(xVals, [self.approximatingFunction(x) for x in xVals], color='red')
		errorText = ax.text(0.005, 0.9, "", transform=ax.transAxes, color="red")
		
		for epoch in range(epochs):
			derivativeWeight0 = 0
			derivativeWeight1 = 0
			for i in range(sampleSize):
				residual = self.calculateResidual(i)
				derivativeWeight0 += (2/sampleSize) * i * residual
				derivativeWeight1 += (2/sampleSize) * residual
			self.weights[0] -= learningRate * derivativeWeight0
			self.weights[1] -= learningRate * derivativeWeight1
			
			if epoch % 50 == 0:
				yPredicted = [self.approximatingFunction(x) for x in xVals]
				line.set_ydata(yPredicted)
				
				errorText.set_text(f"GlobalError: {self.calculateGlobalError()}")
				
				plt.draw()
				plt.pause(0.001)
				time.sleep(0.02)
			
			if abs(lastEpochGlobalError - self.calculateGlobalError()) < tolerance:
				print("learning terminated due to sufficient global error being met")
				break
				

model = LinearRegressor(generatePatternedSeries(500))
model.train(epochs=5000, learningRate=0.001)
```

