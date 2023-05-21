AKA Gradient Flow

A common training algo for [[Neural Networks (NN)]], makes [[Gradient Descent Algorithm]] feasible for multi-layer neural networks.

It's effectively distributing the error weights after NN calculations backwards through the network to the earlier layers.

Before doing backprop you wanna normalise feature values.

I.e Using the [[Chain Rule]] to compute the gradients recursively.

### Error Function

The goal with NN is, of course, to learn the weights of the network automatically from data such that the predicted output is cloose to the target for all inputs.

To measure how far we are from this we use an error func., commonly the following is used:

$$E(y_{output}, y_{target}) = \frac{1}{2}(y_{output} - y_{target})^{2}$$

### Dropout [[Regularization]]

Dropout works by randomly dropping units in a network for a single gradient step, the more you drop out the stronger the regularization.

Works on a scale from 0.0 (drop nothing) to 1.0 (drop everything).

### Common Failure Cases

1. Vanishing Gradients
	1. FIX: Potentially using a ReLU activation func.
2. Exploding Gradients
	1. FIX: Potentially batch normalisation, or lowering learning rate
3. Dead ReLU Units
	1. FIX: Potentially lower the learning rate

See also:
- [[Backpropagation]] in action, thanks papa Google (https://developers-dot-devsite-v2-prod.appspot.com/machine-learning/crash-course/backprop-scroll)
- https://developers.google.com/machine-learning/crash-course/training-neural-networks/video-lecture

