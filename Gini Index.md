# Gini Index

"If we select two items from a population at random then they must be of the same class,  and the probability for this is 1 if the population is pure"

Basically, this is a splitting method for [[Decision Trees]] and the like, but it only performs binary splits (yes/no) with categorical target variables. 

The higher the gini index, the higher the homogeneity of the data.

## How the fuck is it calculated?

For sub-nodes:
Sum of squares of probability for success and failure ($p^2+q^2$).

For each node of that split:
Calculate weighted gini score.