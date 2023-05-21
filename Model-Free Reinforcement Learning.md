A method of [[Reinforcement Learning]] wherein the [[Markov Decision Process]] is unknown and still necessary to solve.

## Methods
- Monte-Carlo: Basically goes all the way to the end of the possible trajectory and estimates the value by looking at sample returns
- Temporal-Difference: Goes one step ahead and estimates after one step
- TD($\lambda$): Unites the two above approaches

Primarily the approach entails:
1. Giving up the assumption as to how the environment works (unrealistic for interesiting problems)
2. Breaking it down into two parts:
	1. Policy evaluation, i.e. how much reward is gained from that policy
	2. Control, i.e. finding the optimum value function and then optimum policy

### Monte-Carlo
We go all the way through the episodes and we take sample returns. So the estimated value function can be the average of all returns. You have to terminate to perform this mean.

It means we use the _empirical mean return_ in place of _expected return_. (by _law of large numbers_, this average returns will converge to the value function as the number of episodes for that state tends to infinity).

### Temporal-Difference
???

## [[Model-Free Control]]


See also:
- [[Reinforcement Learning]]

