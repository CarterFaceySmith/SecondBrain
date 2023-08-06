A hybrid [[Reinforcement Learning]] architecture combining value-based and policy-based methods similar to [[Actor-Critic]], it improves the agent's training stability by avoiding policy updates that are too large. 

## How?

We use a ratio that gives us the difference between the current and old policy, then we clip this ration to a specific range: $[1-\epsilon,1+\epsilon]$

This means our policy update is not too large and the taining is more stable.

This is fucking great, because *generally* smaller policy updates are more likely to converge to an optimal solution. It prevents 'falling off a cliff' where we get a bad policy and sometimes can never recover or take ages to recover.

### [[Clipped Policy Surrogate Function]]

