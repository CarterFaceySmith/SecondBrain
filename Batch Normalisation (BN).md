You want your [[Activation Function]] to not die out right, and you want it to be stable? 

For this the ideal is unit Gaussian activations (for example), where the mean of the mini-batch samples over some feature $k$ is the force unit Gaussian in each dimension of the features.

Further, this combats [[Covariate Shift]].

$$\hat{x}^{(k)}=\frac{x^{(k)}-E[x^{(k)}]}{\sqrt{Var[x^{(k)}]}}$$
How does it function at a high-level for [[Neural Networks (NN)]]?

BN normalises the mean and the variance of the inputs to your activation functions.
It's a layer to be applied after fully connected (convolutional) layers and before non-linear activation functions.

## Implementing Batch Normalisation

$x$: output value
$m$: mean
$s$: standard deviation

1. Normalise the output from the activation function: $z=\frac{x-m}{s}$ 
2. Multiply the normalised output by arbitrary parameter $g$: $z*g$
3. Add arbitrary parameter $b$ to resulting product: $(z*g)+b$

Remember this occurs on a *per-batch* basis, i.e. for each batch.

### What Are We Fucking Doing Here?

Allowing the [[Neural Networks (NN)]] to change the range $y^{(k)}=\gamma^{(k)}x^{(k)}+\beta^{(k)}$ where $\gamma$ and $\beta$ get optimised during [[Backpropagation (Gradient Flow)]] (they are learned like any other parameter, i.e. the network can shift these values).



