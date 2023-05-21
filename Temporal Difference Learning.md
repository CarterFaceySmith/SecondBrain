Temporal Difference learning is a [[Reinforcement Learning]] strategy on how to train the value or policy function.

It waits for one step $S_{t+1}$ to form a TD target and update $V(S_t)$ using $R_{t+1}$ and $\gamma * V(S_{t+1})$.

This updates the value function at each step. It then *estimates* $G_t$ by adding $R_{t+1}$ and the discounted value of the next state.

This is called ***bootstrapping***, because you're basing an update on an existing estimate of the value function and not a complete sample.

