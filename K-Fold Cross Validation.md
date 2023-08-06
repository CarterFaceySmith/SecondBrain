A data validation method used in [[Machine Learning]] to ensure you're not corrupting your results.

We divide the data into k partitions and one partition is assigned the test set, all others k - 1 form the training set.

We then evaluate and repeat, with different partitions as the test set each time.

Finally, we average the results.

See also:
- [[Data Preparation]]
- 