[[1,1 - Neural Network Components]] $\leftarrow$ Back
[[1,3 - Forward Pass]] $\leftarrow$ Next

---
# What are Transfer Functions
Transfer functions are a function, applied to the result of the activation function of a neuron, which converts said result into an output signal of the neuron.
- Denoted as $f_j$ -the transfer function of neuron j.
- Modifies the input signal

The transfer function is what forces a neural network to become non-linear.
- Without transfer functions, NN would act as one large simple linear equation, making it unable to learn complex patterns.

Multiple types of transfer functions exist. Three common choices of transfer function are:
1) Step 
$$
f(e)= \begin{cases}e < 0 \Rightarrow f(e) = 0\\e \geq 0 \Rightarrow f(e) = 1\end{cases}
$$
Cannot use step as it is not differentiable: not continuous
2) Sign
$$
f(e) = \begin{cases}e \geq 0 \Rightarrow f(e)=1\\e < 0 \Rightarrow f(e) = -1\end{cases}
$$
Cannot use sign as it is not differentiable: not continuous 
3) Sigmoid
	- x is the result of activation function in this case to avoid confusion with natural number e.
$$
f(x)=\frac{1}{1+e^{-x}}
$$
4) Tanh

5) ReLU

6) Leaky ReLU
	- Leaky ReLU exists due to ReLU having a gradient when x < 0: doesn't give any directional information to minimise loss function.

7) 