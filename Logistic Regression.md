# Logistic Regression

Instead of predicting exactly 0 or 1, logistic reg gives a probability - a val *between* 0 and 1 exclusive.

Ie gives the probability of what you're trying to predict being the outcome based on prev. data.

### Loss and regularization in logistic regression
While the loss func for [[[Linear Regression]] is squared loss, logistic regression uses log loss which you can bloody well google (or see the handy dandy google dev link below xx).

Regularization is incredibly important specifically for logistic regression modelling, because log regression uses asymptotes for calculations etc it will keep driving loss towards 0, overfitting and causing problems potentially as it drives the weights for each indicator feature to +-infinity. 

Normally this occurs in high dimensional data (a dataset where the number of features p is larger than the number of observations N, often written p >> N).

We use L2 [[Regularization]] or alternatives to combat this.

### Terminology:
- sigmoid: something that gives us a bounded val between 0 and 1 exclusive

![[Screen Shot 2022-03-12 at 2.22.32 pm.png]]

See also:
- [[Machine Learning]]
- [[Linear Regression]]
- https://developers.google.com/machine-learning/crash-course/logistic-regression/model-training