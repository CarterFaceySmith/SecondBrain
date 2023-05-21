AKA Steepest Descent, [[Loss Function]]

An *iterative* optimisation algo for finding the **local** minimum of a function.

The goal of gradient descent is to minimise the given func., which it does by doing the following iteratively:
1. Computes the gradient (slope), the first order derivative of the func. at that point; and
2. Makes a step in the direction opposite to the gradient, steps from urrent point by alpha (learning rate, a tunable param. that decides the length of steps) times the gradient at that point.

 #### Code example (Python)
 X: training data set
 y: labels for training data
 W: weights vector
 B: bias variable
 alpha: learning rate (step size really)
 max_iters: maximum GD iterations
 
 	def train(X, y, W, B, alpha, max_iters):
		dW = 0 //weights gradient accumulator
		dB = 0 //bias gradient accumulator
		m = X.shape[0]
		for i in range(max_iters):
			dW = 0
			dB = 0
			for j in range(m):
				W = W - alpha * (dW / m)
				B = B - alpha * (dB / m)
		return W, B
		

### Stochastic Gradient Descent (SGD)

Wanna get the right gradient *on average* for much less computation? SGD is ya boi, we use a single example (batch size of 1) per iteration of the algorithm, given enough iterations SGD will work but it's very noisy.

#### Mini-batch SGD

A compromise between full-batch iteration and SGD, mini-batch is typically between 10-1000 examples chosen at random.

### [[Backpropagation]]

See also:
- [[Machine Learning]]
- [[Loss Function]]