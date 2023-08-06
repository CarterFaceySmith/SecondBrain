Common [[Loss Function]]s used with [[Generative Adversarial Networks (GAN)]] are minimax and Wasserstein loss.

It is important to note that GANs can have two loss funcs, one for generator training and one for discrim. training. 

## The Maths of Loss

- Discriminator Loss:
	- Binary Cross Entropy
$$J^{(D)}=-\frac{1}{2}E_{x\texttildelow p_{data}}logD(x)-\frac{1}{2}E_{z}log(1-D(G(z)))$$
- Generator Loss:
	- $J^{G}=-J^{D}$

- Minimax Game:
	- $G$ minimises the probability that $D$ is correct, therefore equilibrium is the saddle point of the discriminator loss (I.e. where $D$ provides supervision (gradients) for $G$)


See also:
- https://developers.google.com/machine-learning/gan/loss