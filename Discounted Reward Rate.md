In the context of a [[Reinforcement Learning]] [[Agents]], the initial rewards of the [[Observation Space]] are more probable, thus a discount rate must be calculated to even the odds more or less.

1. Define a discount rate $\gamma$, between 0 and 1, most of the time between 0.99 and 0.95.
	1. Larger $\gamma$ = smaller discount, meaning our agent cares more about the long-term reward, and vice versa for smaller $\gamma$
2. Each reward is discounted by gamma to the exponent of the time step, normally as the time step goes up the future reward is less and less likely to happen

