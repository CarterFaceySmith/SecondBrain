A common training algo for [[Neural Networks (NN)]], makes [[Gradient Descent]] feasible for multi-layer neural networks.

It's effectively distributing the error weights after NN calculations backwards through the network to the earlier layers.

Before doing backprop you wanna normalise feature values.

I.e Using the [[Chain Rule]] to compute the gradients recursively.

### Yeah righto, but what the fuck are you on about?

Ok, so how does backpropagation function at a conceptual level?

You have your network, hypothetically you want a specific output neuron to increase, remembering that the neuron is defined as 'a certain weighted sum of all the activations in the previous layer, plus a bias' which has been plugged into an activation function.

How can you go about nudging that value? You can increase the biases, increase the weights, or change the activation function used.

***Or*** you could change all the activations in the previous layer, right?

I.e. If everything connected to your neuron with a positive weight got 'brighter' and everything connected with a negative weight got 'dimmer' in this context, your neuron would become more active!

You now have a sort of 'desire' value as to what the preceding layer thinks should happen to that neuron (up or down in value, etc).

Let's say you did this for every output neuron, by adding together all these desired effects you have a list of nudges for the second-to-last layer, if you did this recursively for each layer in the network moving backwards you have then adjusted all weights.

Boom, backpropagation.

This occurs every training example normally.

### Error Function

The goal with NN is, of course, to learn the weights of the network automatically from data such that the predicted output is cloose to the target for all inputs.

To measure how far we are from this we use an error func., commonly the following is used:

$$E(y_{output}, y_{target}) = \frac{1}{2}(y_{output} - y_{target})^{2}$$

### Dropout [[Regularisation]]

Dropout works by randomly dropping units in a network for a single gradient step, the more you drop out the stronger the regularisation.

Works on a scale from 0.0 (drop nothing) to 1.0 (drop everything).

### Common Failure Cases

1. Vanishing Gradients
	1. FIX: Potentially using a ReLU activation func.
2. Exploding Gradients
	1. FIX: Potentially batch normalisation, or lowering learning rate
3. Dead ReLU Units
	1. FIX: Potentially lower the learning rate

See also:
- [Backpropagation in action](https://developers-dot-devsite-v2-prod.appspot.com/machine-learning/crash-course/backprop-scroll), thanks papa Google
- [Google Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course/training-neural-networks/video-lecture)

