A combination of Momentum and RMSProp methods regarding a [[Gradient Descent]], where the main idea is the first 'momentum' measure being the mean of combined gradients, and the second being the variance of combined gradients.

The heavy shit:
$$\theta^{k+1}=\theta^k - \alpha \cdot \frac{m^{k+1}}{\sqrt{v^{k+1}+\epsilon}}$$
- $m^{k+1}$ is the mean of gradients, ie the first momentum
- $v^{k+1}$ is the variance of gradients, ie the second momentum

ADAM normally only needs tuning of $\alpha$, and is generally the method of choice for Stochastic [[Gradient Descent]] updates.

This shit converges mad fast but balances risk of overshooting better than others of the same or better speed.