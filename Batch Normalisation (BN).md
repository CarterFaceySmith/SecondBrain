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

## Training and Testing

Train-time: mean and variance is taken over the mini-batch
Test-time: compute the mean and variance by running an exponentially weighted averaged across training mini-batches. $σ^2_{test}$  and $μ_{test}$:
$$Var_{running} = \beta_m*Var_{running}+(1-\beta_m)*Var_{minibatch}$$
$$\mu_{running} = \beta_m*\mu_{running}+(1-\beta_m)*\mu_{minibatch}$$
Note: $\beta_m$ is normally 0.99 but can be changed as a hyperparameter.

## Drawbacks

As you reduce the batch size (< 8), the statistics for mean and variance get less and less accurate and BN starts to deliver poorer results.

The solution? Use [[Layer Normalisation]], [[Instance Normalisation]], or [[Group Normalisation]] (the error stays quite constant despite the batch size).

The non-linearity of BN during training is due to the fact that each batch out of the whole dataset is normalised by different values (mean and standard deviation (std)). 

During the inference time (testing), it is basically considered a linear function, since those values are a constant (running-mean and running-var), that do not depend on the test input.


