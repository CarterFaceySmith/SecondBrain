The Bellman equation simplifies a [[Reinforcement Learning]] state value or state-action value calculation.

Remember that to calculate the value of a state ($V(S_t)$) we need to calculate the return starting at that state then follow the policy forever, it's rather inefficient after a point.

The Bellman equation is a recursive equation that works by considering the value of any state as: the immediate reward $R_{t+1}$ + *the discounted value of the state that follows* $(gamma * V(S_{t+1})$).

## The Full Equation
$$V_\pi(s) = E_\pi[R_{t+1} + \gamma * V_\pi(S_{t+1})|S_t=s]$$
I.e. *The sum of immediate reward + the discounted value of the state that follows*


See also:
- [[Machine Learning]]