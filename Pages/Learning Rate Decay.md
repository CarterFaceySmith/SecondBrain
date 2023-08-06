You have a key issue with learning rates, you need a high learning rate when far away from the minima and a low learning rate when closer to narrow down on it without overshooting.

Currently the solution to this is a decay value at a set step/time interval.

## Decay Rate Formula
$$\alpha = \frac{1}{1+decay\_rate*epoch}\cdot \alpha_0$$
E.g. $\alpha_0 = 0.1 * decay\_rate = 1.0$

So each epoch the value should get smaller and smaller.

Alternative is step decay: $\alpha = \alpha - t \cdot \alpha$ where $t$ is the decay rate (normally 0.5)

\See also:
- [[Machine Learning]]