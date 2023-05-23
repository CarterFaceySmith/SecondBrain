Penalising the complexity of a [[Machine Learning]] model to reduce overfitting.

We want to avoid model complexity where possible. But note that this also increases potential training error, at the tradeoff of reducing overfitting.

### Early Stopping

Simply stopping the training before you converge on the training data, but this can be difficult to pull off.

### L2 Regularisation

$$
complexity(model) = sum(weights^2) = \lambda(L2Norm^2)
$$
Where $\lambda$ is a scalar value that controls how the weights are balanced

This method of regularisation penalises massive weights, encourages weights to be small , butdoesn't force them to exactly 0.0.

We add this term to our loss function, to get:
`minimise: Loss(Data | Model) + complexity(Model)`

Model complexity can be thought of in two ways:
1. the function of the *weights* of all the features in the model; or
2. a function of the total number of features with nonzero weights.

### Sparsity

x

### L1 Regularisation

Penalises the sum of `abs(weights)`, encouraging sparsity.

Let's say you've got a massive fuck-off dataset, you've done a few too many [[Feature Cross]]es, god that'd be expensive for RAM usage and the like right? It'd be nice if we could encourage weights to go to **zero** where possible/irrelevant, right? Let's force a few to exactly 0.0 using L1 Regularisation.


See also:
- https://developers.google.com/machine-learning/crash-course/regularization-for-simplicity/video-lecture
- [[Feature Cross]]
- [[One-Hot Encoding]]
- [[Data Preparation]]