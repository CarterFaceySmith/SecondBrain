# Naive Bayes

A naive bayes classifier is a probabaility classifier based on Bayes theorem that allows us to model probability of classification of a new data point given pre-exisiting data points.


### Bayes Rule

There is a prior (the prob before we run any test), you then receive test evidence, these combine to create the posterior probability.

Example where C is a positive result for cancer:
Prior = P(C) = 0.01
Posterior(C | Pos) = P(C) x P(Pos | C)			(prior, times the probability of a cancerous result)
							   = P(not C | Pos) = P(not C) x P(Pos | not C) 		(prior not C, times the prob of a non-cancerous result)

Note:
- P of not C is always 1 (100%) - P(C), therefore 0.99 or 99%
- P (Pos | C) = 0.9
- P (Neg | not C) = 0.9
- P (Pos | not C) = 0.1


### Normalisation

- P(Pos) = P (Pos | C) + P (Pos | not C) = 0.009 + 0.099 = 0.108

Final posterior for cancer version = P (Pos | C) / Normalised P(Pos) Value = 0.009 / 0.108 = 0.0833
Final posterior for noncancer version = P (Pos | not C) / Normalised P(Pos) Value = 0.9167

Therefore the total probability is both final posteriors summed up, which is 1.

See also:
- [[Machine Learning]]
- SciKit Documentation on Naive Bayes and Gaussian variant
- Udacity Machine Learning COurse: Lesson 2 - Naive Bayes
