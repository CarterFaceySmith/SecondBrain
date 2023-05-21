# Classification

Instead of continuous or real-valued outputs, the outputs of classification problems are discrete labels or classes.

Examples include image recognition, sentiment recognition, medical diagnosis, etc.

Binary = only two possible labels
N-ary = more than two possible labels

First we define a classification threshold (AKA decision threshold), ie the point at which x is classified as y.


### True Positives and False Positives (Confusion Matrix)

- True Positive (TP): little boy says wolf, there was a wolf
- False Positive (FP): little boy falsely calls wolf, there was no wolf
- False Negative (FN): little boy did not call wolf, there was a wolf
- True Negative (TN): little boy did not call wolf, there was no wolf

### Evaluation Metrics

Accuracy: number of correct predictions / total num. of predictions
	- more specifically for binary classification:
			(TP + TN) / (TP + TN + FP + FN)
 But accuracy measures are prone to misanalysis depending on the dataset and problem, so we use better shit below.
 
Precision: (TP) / (TP + FP), what proportion of positives were actually correct
Recall: (TP) / (TP + FN), what proportion of actual positives was *identified* correctly

### ROC Curves and AUC

A Receiver Operating Characteristic Curve (ROC Curve) is a graph that shows the performance of a classification model at all classification thresholds (see above), by plotting true positive rate and false positive rate.

TPR = (TP) / (TP + FN)
FPR = (FP) / (FP + TN)

#### But how the fuck do we compute the points in an ROC Curve without doing a shit tonne of [[Logistic Regression]] to evaluate models at diff classification thresholds?

We use AUC baby. Area-Under-the-Curve, it measures the two-dimensional area underneath the ROC curve from (0,0) to (1,1).


