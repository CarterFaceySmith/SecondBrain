A stored memory of a previous action, an experience sample that can be reused during training, allowing the agent to learn from the same experiences multiple times.

Prevents the [[Neural Networks (NN)]] from only learning about what it has done immediately before.

By randomly sampling experiences we also remove correlation in the observation sequences and avoid weird oscillations and divergence in action values.


See also:
- [[Deep Q-Learning]]