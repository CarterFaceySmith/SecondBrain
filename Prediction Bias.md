# Prediction Bias

Prediction bias = avg of predictions - avg of labels in dataset

Measures how far apart the two averages are as a form of bias.

Significant non-zero outcome shows there is a bug somewhere in your model as the model is wrong about how frequently positive labels occur.

### Bucketing

A sort of cross-section/grouping of examples (into 'buckets'), those that are similarly grouped together. 

Normally formed via quantiles or linearly breaking up the target predictions.

### Calibration Layers

A post-prediction adjustment, normally to account for prediction bias, this is normally not a good idea man, you can end up becoming over-reliant on them and in time maintaining them will become more trouble than it's worth.

See also:
- [[Logistic Regression]]
