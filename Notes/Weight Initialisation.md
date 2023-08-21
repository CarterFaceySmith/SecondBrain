An important aspect of training [[Neural Networks (NN)]] is initialisation of the weights for use by the network, remember that [[Gradient Descent]] it is not guaranteed to reach the optimum for different starting points.

If $w=0$ at the start, the hidden units compute the same function (gradients will be the same), so it would be like you only had one neuron, shit and useless.

So you initialise them randomly right? Gaussian, mean centered at 0. Well what is you get small numbers and therefore vanishing gradients from the small outputs of layer 1? Or big numbers and vanishing gradients due to a saturated [[Activation Function]]?

## Xavier Initialisation

Ensures the variance of the output is the same as the input, Gaussian.

$Var(w) = \frac{1}{n}$

Xavier: $W$ ~ $U[-\frac{1}{\sqrt{n}},\frac{1}{\sqrt{n}}]$ 

Alt. Kaiming (He) Initialisation: $W$ ~  $N[0,\frac{2}{n}]$ 

Note: Xavier init. is shit with ReLUs, they kill exactly half the data, to fix it you need to multiple the entire thing by 2, i.e $Var(w)=\frac{1}{n/2}=\frac{2}{n}$.




