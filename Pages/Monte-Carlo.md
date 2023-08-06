Monte-Carlo learning is a [[Reinforcement Learning]] strategy on how to train the value or policy function.

Monte-Carlo uses an entire episode of experience before learning, i.e. it waits until the end of the episode, calculates $G_t(return)$ and uses it as a target for updating $V(S_t)$.
