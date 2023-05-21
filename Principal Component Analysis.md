A [[Dimensionality-Reduction]] method, like [[Embeddings]], that transforms a large dataset into a smaller one that still contains most of the info in the larger set.

A simple idea, reduce the num. of vars while preserving as much data as possible.

### What the fuck are *principal components*???

New vars constructed as linear combos of initial vars, such that the new vars are uncorrelated and most of the info from the initial vars is compressed into the components.

So for each dimension of the data we want a corresponding principal component, with PCA specifically trying to fit as much info as possible in the first component then doing the same for the next, and so on, diminishing as it goes.


![Percentage of Variance (Information) for each by PC](https://builtin.com/sites/www.builtin.com/files/styles/ckeditor_optimize/public/inline-images/national/Principal%2520Component%2520Analysis%2520Principal%2520Components.png)


We can then discard components with low info and consider the remaining components our new vars.

> To put all this simply, just think of principal components as new axes that provide the best angle to see and evaluate the data, so that the differences between the observations are better visible.

### Five steps to enlightenment

#### One: Standardization

AKA standardizing the range of continuous vars so that each can have the opportunity to shin and contribute equally to analysis like the special bois they are.

We do this mathematically by doing the following equation for each value of each var, but the program does this for us so fuck memorising it. (this is just here for if you're curious xx)
$$
z = \frac{value - mean}{standard\ deviation}
$$

#### Two: Covariance Matrix Computation

AKA sussing if there is any relation between the vars because we dont need redundant info in our computations bb

> The covariance matrix is a _p_ × _p_ symmetric matrix (where _p_ is the number of dimensions) that has as entries the covariances associated with all possible pairs of the initial variables.

But what tf is the point of this info, well basically if the sign of a covariance is pos. the two vars increase or decrease together, ie are correlated, and if it's neg. then one increases when the other decreases, ie inversely correlated.

Now we do more shit.

#### Three: [[Eigenvectors]] and eigenvalues

Remember that every eigenvectors has a paired eigenvalue, and their number is equal to the number of dimensions in the data, eg 3-dimensional data has 3 eigenvectors and 3 corresponding eigenvals.

Now my boy, here's the rub. 

Eigenvectors of the covariance matrix above are actually, get this, *the directions of the axes where there is the most variance (therefore information spread)*.

Eigenvalues are just the coefficients attached to those eigenvectors which give the most amount of variance carried in each principal component.

Order those bad bois by their eigenvalues in descending order and you now can find the principal components in order of significance, exciting stuff.

#### Four: Feature Vectors

Now we choose whether to keep all principal components or discard those with less significance (low eigenvalues), then form a matrix of vectors with those remaining called a feature vector.

So, a feature vector is simply a matrix with columns being the eigenvectors of the components we decided to keep.

#### Five: Recast the data along the new principal component axes

We do this by multiplying the matrix transpose of the original dataset by the matrix transpose of the feature vector. You may wanna have a look at the transpoes link if need be.

See also:
- https://builtin.com/data-science/step-step-explanation-principal-component-analysis
- [[Data Preparation]]
- https://mathinsight.org/matrix_transpose


