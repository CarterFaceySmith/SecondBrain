#### Sigmoid (Binary Classification)
- Converts weighted sum to a val. between 0 and 1.
- Gives a probability of the output class being 0 or 1.
$$F(x) = \frac{1}{1+e^{-x}}$$

### TanH

#### ReLU (Rectified Linear Unit)
- Standard choice most of the time
- Often a little better than a smooth func. like a sigmoid whilst being easier to compute.
$$F(x) = max(0,x)$$
##### Dead ReLU
- If at some point the neuron produces a negative output it cannot recover and dies off, this is the dead ReLU problem.
- Can be avoided by initialising the ReLu neurons with a slight positive bias (0.01 or so), making it likely they will stay active for most inputs

##### Leaky ReLU
- Combats Dead ReLU by changing the func to $F(x) = max(0.01,x,x)$
- Common in [[Generative Adversarial Networks (GAN)]]

##### Parametric ReLU
- Parameter $\alpha$ instead of 0.01 in Leaky ReLU, that is trained of neural network (One more parameter to [[Backpropagation (Gradient Flow)]] into)
- Good at combating Dead ReLU
$$F(x) = max(\alpha x,x)$$

#### Softmax (Multiclass Classification)
- The current gold standard activation function for multiclass uses, paired with [[Cross-Entropy Loss (Maximum Likelihood Estimate)]].
- For each class we have a set of weights that correspond to the respective classes, these produce a score function for those classes.
- Takes the weights and scores for each class, produces a probability distribution for the respective classes.

$$p(Y_i|x_i,\Theta) = \frac{e^{S_{y_i}}}{\sum^C_{k=1}e^{S_k}}=\frac{e^{{x_i}\theta_{y_i}}}{\sum^c_{k=1}e^{{x_i}\theta_k}}$$

The above formula is the probability of the true class where:
- $y_i$: Label (true class)
- $\Theta = [\theta_1,\theta_2\dots]$
- $C$: Number of classes
- $s$: Score of the class

- The upper half of the fraction is the exponential operation, makes sure the probability stays above 0.

- The lower half is the normalisation, makes sure the probabilities sum to 1.

#### ELU

#### Maxout
- Train parameters with other parameters of the network. 
- Piecewise linear approximation of a convex function with $N$ pieces → Generalisation of ReLUs, Linear Regimes
- Does not die, does not saturate, BUT Increases number of parameters
$$max(w_1^Tx+b_1,w_2^Tx+b_2)$$ ![[Screenshot 2023-06-11 at 1.07.49 pm.png]]

