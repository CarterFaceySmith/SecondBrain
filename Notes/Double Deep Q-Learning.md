A method that is rather nice at handling overestimation of Q-values.

First off, remember how a [[Temporal Difference Learning]] target is calculated.

How are we sure the best action for the next state is the action with the highest Q-value given the accuracy problems Q-values can have??

## So what the fuck do we do about this?

We use **two** networks to *decouple* the action selection from the target Q-value generation, clever no?

1. Use our [[Deep Q-Learning]] network to select the best action to take for the next state (highest Q-value)
2. Use our target network to calculate the taarget Q-value of taking that action athe next state.

