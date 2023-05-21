# SVM (Support Vector Machines)

An algorithm that takes input data and outputs a classification line that maximises the margin (distance to all nearest points), after ensuring all points are classified correctly, based on that data.


### Parameters
- gamma = how much curvature we want in the decision boundary
	- technical answer: how far the influence of a single training example reaches, lower = further and vice versa
	- so a low gamma val takes into account datapoints further away from the decision boundary along with those closer, wheras a high gamma val will take into account datapoints closer to it and disregard those further away

- c = controls the tradeoff between smooth decision boundary and classifying of points correctly, larger = smaller margin accepted if classification is better and vice versa

- [[Kernel Trick]]



Notes:
- When passing data in for prediction, only one data (eg features, or labels) part is fed in, the other part is what is being predicted.
- Sometimes the data may seem not linearly seperable but after transforming or adding a feature, the data can be made seperable.
- Remember to be cautious of overfitting (generalization) when determining param values

See also:
- [[Machine Learning]]
- [[Kernel Trick]]
- [[Linear Regression]]
- SKLearn SVM Documentation