Penalising the complexity of a [[Machine Learning]] model to reduce overfitting.

We want to avoid model complexity where possible. But note that this also increases potential training error, at the tradeoff of reducing overfitting.

You are effectively forcing the model to learn better features.

### Early Stopping

Simply stopping the training before you converge on the training data, but this can be difficult to pull off.

### Dropout

Dropout works by randomly dropping units in a network for a single gradient step, the more you drop out the stronger the regularisation.

Works on a scale from 0.0 (drop nothing) to 1.0 (drop everything). Typically 50%.

It is then disabled at testing time, dropout only used in training. This does propose the issue that training and test conditions are different right? So you add a dropout probability offset at test time based on the percentage you dropped out.

#### Monte-Carlo Dropout

Basically you run a network multiple times at training with a low probability of dropout (01 or 0.2) and check its predictions:
- If it consistently predicts the same thing it is confident
- Vice versa = not confident

It is producing a confidence estimate you can apply.

### L2 Regularisation

$$
complexity(model) = sum(weights^2) = \lambda(L2Norm^2)
$$
Where $\lambda$ is a scalar value that controls how the weights are balanced

This method of regularisation penalises massive weights, encourages weights to be small , but doesn't force them to exactly 0.0.

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

### Bagging and Ensemble Models

You could also regularise by training multiple models and averaging their results. 
E.g. Use a different optimisation algorithm or change the objective/loss function.

If errors are uncorrelated, the expected combined error will decrease linearly with the ensemble size.

See also:
- [Google Machine Learning Crash Course: Regularization](https://developers.google.com/machine-learning/crash-course/regularization-for-simplicity/video-lecture)
- [[Feature Cross]]
- [[One-Hot Encoding]]
- [[Data Preparation]]
- [[Data Augmentation]]