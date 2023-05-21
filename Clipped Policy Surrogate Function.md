A policy function used in clipping a [[Proximal Policy Optimisation (PPO)]] step size, constraining the policy update to avoid destructively large weights updates.

$$L^{CLIP}(\theta)=\hat{E}_t[min(r_t(\theta)\hat{A}_t,clip(r_t(\theta),1-\epsilon,1+\epsilon)\hat{A}_t)]$$

- $r_t(\theta)$ is the ratio function, the probability of taking action $a_t$ at state $s_t$ in the current policy divided by the same for the prev. policy
	- I.e. if it is greater than 1 the action is more likely in this policy than the old policy and vice versa for between 0 and 1
	- Good estimate of divergence between policies



See also:
- https://huggingface.co/learn/deep-rl-course/unit8/clipped-surrogate-objective?fw=pt
- 

