The task is to approximate an unknown target function using attributes given to a ML model, we need:
- the hypothesis (what we're trying to predict);
- evidence/experience (the training dataset);
- performance measure (how we determine how well the hypothesis matches the experience);

When creating a model, it is necessary to think about 'model capacity', which is the limitations of what the model can model, ie a [[Linear Regression]] model can only model a line, does not have the *CAPACITY* to represent the data

### [[Loss Function]]
A measure of the performance of the ML model, our goal being to minimise this.

### Dynamic vs. Static ML Training

Static models are trained offline, using pre-available data. Easier to build and test.

Dynamic models are trained online with new data constantly streaming in and tweaking the model. More adaptable to changing data.

### Dynamic vs. Static Inference

Static (offline) inference means you are making all possible predictions in a batch, whilst dynamic (online) inference means you are predicting on demand using a ML model on a server.

See also:
- [[Supervised Learning]]
- [[Unsupervised Learning]]
- [[Data Science]]
- [[Linear Regression]]
- [[Multiple Linear Regression]]
- https://developers.google.com/machine-learning/crash-course/static-vs-dynamic-inference/video-lecture