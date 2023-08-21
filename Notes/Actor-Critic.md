A hybrid [[Reinforcement Learning]] architecture combining value-based and policy-based methods to help stabilise the training through variance reduction.

## What?

Basically:
- An *actor* that controls how the agent behaves (this is the policy-based method)
- A *critic* that measures how good the taken action is (value-based method)

Addresses variance concern, ya see, the advantage of reinforcing state-action pairs based on [[Monte-Carlo]] sampling is that it is unbiased, we aren't estimating the return just the true *obtained* return.

BUT.

Given the stochastic nature of the environment (randomness), this can lead to wild return difference from the same starting state across episodes, i.e. ***variance***. You can't simply increase the batch size either because it reduces sample efficiency.

### The Actor

A policy for controlling how the agent acts: $\pi_\theta(s)$

### The Critic

A value function to assist the policy update by measuring action 'goodness': $\hat{q}_w(s,a)$ 

### The Process

- At each timestep, $t$, we get the current state $S_t$ from the environment and pass it as input through our Actor and Critic
- Our policy takes that state and outputs action $A_t$
- Critic takes that action and using $S_t$, computes the value of taking that action at that state, the Q-value
- The action performed creates a new output state $S_{t+1}$ and a reward $R_{t+1}$
- Actor updates policy parameters using the Q-value, this produces the next action given the new state
- The Critic then updates its value parameters

## Advantage Function

Learning can be stabilised further using the Advantage Function as Critic instead of the Action value function.

This function calculates the *relative advantage* of an action compared to the others possible at a state, it is subtracting the mean value of that state from the state-action pair.
$$A(s,a) = Q(s,a) - V(s)$$

I.e. It calculates the extra reward we get if we take this action at that state compared to the mean reward we get at that state.
