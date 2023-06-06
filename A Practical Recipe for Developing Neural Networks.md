## Overview
1. You have a dataset with labels:
		- ${x_i,y_i}$
			- $x_i$: the $i^{th}$ training image with label $y_i$
2. Split your data into train, test and validation sets
3. You then take a network $f$ with parameters $w, b$
4. Use Stochastic [[Gradient Descent]] (or a variation like [[Adaptive Moment Estimation (ADAM)]]) to find the optimal $w, b$ parameters
5. Try to optimise your hyper-parameters either manually or via grid search/random search

### How To Start
1. Start with a single training sample and overfit
	- You just want to check that the output is correct for your model, the training accuracy should be 100% because the input is just memorised.
2. Increase to a handful of samples (E.g. 4)
	- Again, check if the input is handled correctly
3. Move from overfitting to more samples (E.g. 100, 10000, 100000)
	- At some point you should see generalisation

## Finding a Good Learning Rate
- Use all training data with a small weighted decay
- Perform an initial loss sanity check based on final layer function
	- E.g. $log(C)$ for softmax with $C$ classes
- Find a learning rate that makes the loss drop significantly (exponential) within **100** iterations
- Some good standard learning rates are: 1e-1, 1e-2, 1e-3, and 1e-4

## Train, Test, Validation Set Rules
- Typical data splits:
	- Train (60%), Val (20%), Test (20%)
	- Train (80%), Val (10%), Test (10%)
- Use the training set for training the [[Neural Networks (NN)]]
- Use the validation set for hyper-parameter optimisation and checking generalisation progress
- Use the test set only at the very end to check the finalised model

## General Tips
- Keep the *training* phase **efficient**. You should be rapidly able to determine any issues with your model or data, you don't want to waste time in this phase.
- Bad signs:
	- Training error not going down
	- Validation error not going down
	- Performance on validation is better than on training
	- Tests on training set different than during training
- Look for potential or real bottlenecks, e.g. dataloading, compressions, [[Backpropagation (Gradient Flow)]], etc.

### Error Tips
- Training error high? You have a bias issue. Basically the model likely doesn't have enough capacity for the task. Get a bigger model, train longer or use a new model architecture (I.e. number of layers, weights, etc.).
- Train-Dev error high? You have a variance issue. Give the model more data, regularise or use a new model architecture.
- Dev error high? You have a train-test data mismatch. Make the training data more similar to the test data, use data synthesis (domain adaptation) or use a new architecture.
- Test error high? You are likely overfitting to the dev set. Get more dev set data.


