AKA Steepest Descent, [[Loss Function]]

$$x^*=argMinf(x)$$

An *iterative* optimisation algo for finding the **local** minimum of a function.

The goal of gradient descent is to minimise the given func., which it does by doing the following iteratively:
1. Computes the gradient (slope), the first order derivative of the func. at that point; and
2. Makes a step in the direction opposite to the gradient, steps from urrent point by alpha (learning rate, a tunable param. that decides the length of steps) times the gradient at that point.

### Code Example (Python)

 $X$: training data set
 $y$: labels for training data
 $W$: weights vector
 $B$: bias variable
 $\alpha$: learning rate (step size really)
 $maxIters$: maximum GD iterations
 
```
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
```

### Stochastic Gradient Descent (SGD)

Wanna get the right gradient *on average* for much less computation? SGD is ya boi, we use a single example (batch size of 1) per iteration of the algorithm, given enough iterations SGD will work but it's very noisy.

#### Mini-batch SGD

A compromise between full-batch iteration and SGD, mini-batch is typically between 10-1000 examples chosen at random.

Note that a sample is only ever in one of the mini-batches, the mini-batches do not overlap in terms of data sampling.

### Gradient Descent with Momentum

We wanna modify GD so that we converge faster and do fewer update steps ideally, we can try to do this by applying a momentum approach. 

This is basically the exponentially-weighted average of the gradient.

##### The Details

$AR$ = Accumulation Rate (AKA Friction or Momentum)
$v$ = Velocity [[Vectors]] scalar of current step
$\alpha$ = Learning rate
$\nabla_\theta L(\theta^k)$ = Gradient of current minibatch

$$AR = v^{k+1}=\beta \cdot v^k - \alpha \cdot \nabla_\theta L(\theta^k)$$

I.e. "Take the current gradient, add it to the previous gradient, and keep summing up."

Note this can result in you overcoming a local minima but it does not guarantee finding the *best* minima as you can overshoot.

##### Nesterov Momentum/Look-ahead Momentum

x

##### [[Adaptive Moment Estimation (ADAM)]]


### [[Backpropagation (Gradient Flow)]]

See also:
- [[Machine Learning]]
- [[Loss Function]]