An Agent operating in an environment can sense the environment and learn how to reach the goal or complete the associated task based on reward signals.

E.g. a chess bot.

The action set is the set of all possible actions the Agent can take in it's current circumstances. 

How the Agent processes and executes actions is represented by a transition function.

The reward function provides the Agent necessary reinforcement for correct actions, it's normally a continuous real number value. E.g the Agent receives a -5 reward function if it moves away from the goal and a +5 if it moves closer.

The **policy function** provides the action to choose in any state, with the optimal policy to execute denoted by $\pi^*$.

The **value function** is the measure of worth of each state, with the value of the state increasing as the Agent gets closer to the goal by that state. Denoted by $v_\pi(s)$.

In summary: the agent loops through state, action, reward, next state with the goal to maximise its cumulative reward.

### Maximising the reward function

Generally you have an equation representing a future reward, this is then discounted (ie scaled down) to help analyse convergence and take into account the uncertainty of environment stochasticity (probabilities).

A good strategy for an agent is to always choose an action that maximises the discounted future reward.

### [[Markov Decision Process (MDP)]]

### The two types of reinforcement learning
- Model-based RL: the reward and transitiion functions are known
- [[Model-Free Reinforcement Learning]]: the reward and transition functions are not known and need to be discovered through testing normally

#### Subtypes
- Value-based: Learn the state or state-action value (value function) then act by choosing best action in state
- Policy-based: Learn the stochastic (probability) policy function that maps state to action then acts by sampling policy
	- Deterministic: a policy at a given state will always return the same action
	- Stochastic: a probability distribution over actions is returned

### [[Q-Learning]]

See also:
- [[Machine Learning]]