KNN is an algorithm primarily used in [[Machine Learning]] that works under the assumption similar things (datapoints) exist in close proximity, i.e near each other based on straight line distance (euclidean distance).

High level Sequence of the Algorithm:
1. Load in data
2. K is initialised to chosen num of neighbours
3. For every data point:
	1. Distance between query example and current example is calculated
	2. Distance and index is added to an ordered collection
4. Ordered collection is ordered ascending by distances
5. The first K entries are picked from sorted collection
6. Labels of K entries gotten
7. If regression, we return the mean of the K labels
8. If classification, we return the mode of the K labels


Note:
- K cannot go below 1 and as it goes towards 1 predictions become less stable
- The reverse is also true for going above one, up to a certain point this will increase prediction stability
- Normally K is made an odd number for tiebreak purposes when we're doing a majority vote, ie picking the mode in classification)