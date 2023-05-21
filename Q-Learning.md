Rephrases a [[Reinforcement Learning]] problem in terms of the Q-function, which is similar to a value func. in that it measures the worth of a state-action pair.

The Q comes form 'quality', i.e. the quality of the action in that state.

The Q-function can be rewritten to be recursive, this basically allows you to generate a value function with only some of the necessary attributes available to you, instead of all of them.

Generates a Q-Table if recursive, it will then continue until a value function is generated I believe. I.e. the agent roams the world and continually updates itself based on it's learnings via the q-value function.

![[Screen Shot 2023-04-06 at 6.01.58 pm.png]]

## Off-policy vs. On-policy

In the context of [[Reinforcement Learning]], off-policy uses a different policy for acting (inference) and updating (training).

I.e. The Q-Learning epsilon-greedy policy is used for acting, whereas the greedy policy is used to select the best next-state action value to update our Q-value (updating).

On-policy uses the same policy for acting and updating.

## [[Deep Q-Learning]]

See also:
- Model-free [[Reinforcement Learning]]
- MIT Introduction to Deep Reinforcement Learning Lecture