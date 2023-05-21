Given a sufficiently large state space, creating and updating a Q-table becomes inefficient, meaning the best idea is then to apporximate the Q-values instead of a Q-table using a parameterised Q-function $Q_\theta(s,a)$.

This approximates, given a state, the different Q-values for each possible action at that state, that's all deep Q-Learning is baby.

## Notes On Relative Instability

Compared to standard [[Q-Learning]] this might suffer from more instability. Why? Because we are combining a non-linear Q-value func. ([[Neural Networks (NN)]]) with bootstrapping (updating targets with existing estimates and not an actual complete return).

### Make it more stable then?

1. [[Experience Replay]] to make more efficient use of experiences
2. [[Fixed Q-Target]]
3. [[Double Deep Q-Learning]] to handle overestimation of Q-values


## The Deep Q-Learning Algorithm

Instead of updating the Q-value of a state-action pair directly like in [[Q-Learning]], we create a loss function that compares our Q-value prediction and the Q-target, then uses the [[Gradient Descent Algorithm]] to update the weights of our network and approximate the Q-values better.

### Phase One: Sampling

We perform actions and store the observed experienced tuples in replay memory.

### Phase Two: Training

We select a small batch of those tuples at random, then learn from that batch using the [[Gradient Descent Algorithm]] update step.

