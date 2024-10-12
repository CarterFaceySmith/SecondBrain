Multicollinearity is like when you have a group of friends who are all so similar that it's hard to tell who's influencing what. 

In statistical terms:

1. **Definition**: Multicollinearity occurs when two or more independent variables in a regression model are highly correlated with each other.
2. **What it looks like**: Imagine you're trying to predict house prices based on square footage and number of rooms. If bigger houses always have more rooms, these variables are multicollinear.
3. **Why it's a problem**:
    - It makes it hard to figure out which variable is actually causing the effect you're seeing.
    - It can make your model unstable - small changes in the data can lead to big swings in your results.
    - It can inflate the variance of your coefficient estimates, making them less reliable.
4. **How to spot it**:
    - Look at correlation matrices
    - Calculate Variance Inflation Factors (VIF)
    - Check condition numbers of the correlation matrix
5. **What to do about it**:
    - Remove one of the correlated variables
    - Combine the correlated variables into a single feature
    - Use [[Regularisation]] techniques like ridge regression
    - Collect more data (sometimes this helps!)
6. **When it's okay**: Sometimes multicollinearity doesn't matter, like if you're only interested in predictions and not in understanding individual variable effects.

Remember, multicollinearity is about relationships between your independent variables, not between independent and dependent variables.


See also:
- [[Statistics]]