Remember that when we calculate the [[Temporal Difference Learning]] error, the loss, we calculate the difference between the TD-target (Q-Target) and current Q-value (estimation of Q).

But wtf, we don't have any clue about the real TD target, we're estimating it. ***Aaaand*** we are using the same parameters (weights) for estimating the TD target and the Q-value! Massive correlation problems. Meaning, our Q-values can shift but so will the target value, tricky to catch a moving target no?

So what do we do instead?

Use a seperate network with fixed parameters for estimating the TD target then copy the parameters from our [[Deep Q-Learning]] network at every $c$ step to update the target network.



