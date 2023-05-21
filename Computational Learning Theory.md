# Computational Learning Theory

Have a think, do you reckon it's possible to measure the likelihood a 'learner' (a ML algo) will produce a reasonable hypothesis of an unknown target func. from a given set of training data?

### PAC Learning (Probably Approximately Correct Learning)

We use PAC learning to examine this bullshit, basically:
	A generated hypothesis (h) in the hypothesis space (H) is approximately correct if its error over the distribution of inputs is bounded by some value (epsilon) such that:
		$$ 0 <= epsilon <= \frac{1}{2}\ $$

###  The basics of the Vapnik-Chervonenkis dimension (VC-dimension)

An alternative approach to measuring the complexity of a hypothesis space, measures "the number of distinct instances of the entire state space of a target func. that a hypothesis can completely discriminate", or in plain english, how many unique instances of the state space there are.

#### Shattering

A set of instances can be shattered if a hypothesis space (HS) is capable of partitioning every sub-set of those instances distinctly.

For a set of instances S, there are 2^abs(S) ways of partitioning the instances, if a hypothesis space H can represent all of these then it shatters S.

The VC-dimension (VC(H)) of a HS is the largest finite subset of the state space that H can shatter (ie represent distinctly)



See also:
- [[Machine Learning]]
	