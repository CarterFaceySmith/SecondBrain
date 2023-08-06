First, understand that a regression line is a straight line that's as close to all datapoints at once as possible, ie smack bang in the middle of them all ideally.

In linear regression, you're attempting to model a relationship between two variables by fitting this regression line (which takes the form of a linear equation, $y = mx + b$) to the observed data on a graph.

In this context x is the explanatory var (the factor that can influence the dependent var), y is the dependent var (the val relies upon the explanatory var), the slope of the line is b, and a is the intercept (the val of y when x = 0). Remember back to the maths bootcamp for this concept.

## [[Score Function]]

#### Finding a relationship and the correlation coefficient

Normally before attempting this you would see if there is a relationship between the variables by using a scatterplot, if the scatterplot looks like there might be then linear regression could be a good call, if it doesn't then you might not get anything useful out of the regression. 

The correlation cooefficient is the "numerical measure of association between two vars", indicated by a val between -1 and 1. This is a good secondary measure to see if linear reg is a good call. The formula is mad complex, so just google that shit.

#### Least-Squares Regression

This is simply one method for fitting a regression line.

Calculates the best fitting line for the observed data by minimising the sum of the squares of the vertical deviations from each data point to the line (how far is the data point from the regression line).

The goal of simple linear reg is to create a model that minimises this. You can compare the result to a least-squares that has only used the mean line (ie the line where the independent var doesnt exist), to see effectiveness.

##### But how do you do this shit?

Well let's get into it:
1. Make your scatterplot and ensure it's scaled correctly (start the axises one point before the lowest val for that axis)
2. Look for a visual line, ie do the datapoints fall along a rough line? If no, linear reg is not a good call
3. Find the mean of each var, graph this on the graph (its a point, called the centroid), this point must be paseed through or your line is not the best fit line
4. Go through the calculations (the comp does this for us thank god)


#### Then we get into the big daddy [[Multiple Linear Regression]]

#### Polynomial linear regression

Simply linear reg with more vars, a special case form of [[Multiple Linear Regression]] which estimates the relationship of data as an nth degree polynomial.

#### Use cases for linear regression

Any time a continuous real num can be predicted as the singular goal, eg stock price prediction, predicting hospital length of stay, etc.

See also:
1. http://www.stat.yale.edu/Courses/1997-98/101/linreg.htm
2. https://www.youtube.com/watch?v=ZkjP5RJLQF4
3. [[F-Tests]]
4. [[Machine Learning]]