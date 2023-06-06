Let's say you have a complex classification problem where the [[Decision Surface]] is not a line, this is a chance to use either [[Feature Cross]] or neural networks.  AKA a perceptron.

### High-level Summary

- You have a set of nodes representing neurons, organised in layers;
- A set of weights representing connections between each NN layer and the one beneath it;
- A set of biases, one for each node; and
- An activation func. that transforms the output of each node in a layer, different layers are allowed different activation functions.

*Sooo*, let's say you have a black and white image to encode, its made up of 24x24 integer values from 0 to 255 representing that pixels brightness, each of these integer values is an input node (ie the zeroth layer of your network).

We will now refer to those as $x_n$ where $n$ is simply the index of the node. But let's start at $x_0$.

The next layer adds a weight $w_0$ value and a bias $b_0$ value, the weight value is added by taking the dot product of it and the input value $x_0$. *Then* the bias value is simply added, standard addition, no fancy shit.

Boom, input layer and a first hidden layer. This is the bit where you run into the linearity issue described below, but let's continue for a sec.

*Now*, the next node is calculated using an activation function to avoid that shit linearity issue. For example if you were using ReLU the next node is simply: $ReLU(x_0)$, so $x_1 = g(w_0 \cdot x_0 + b_0) = ReLU(x_0)$.

Then this process repeats for the next layer, passing forward through the network until you get to the output layer where it is encoded based on your purposes, i.e. via softmax or something else.

### Breaking this shit down

You have a linear model as a graph here, blue nodes are input features and green are weighted sum of the inputs (ie output).

![Three blue circles in a row connected by arrows to a green circle above them](https://developers.google.com/machine-learning/crash-course/images/linear_net.svg)

You can add hidden layers that process the inputs further before calculating output, but it would still be a linear combination of its inputs right? Multiplying matrices by matrices simply gives another matrix right? So the model still can't bloody deal with nonlinear problems.

So what do we do? We add a nonlinearity directly into the model as a nonlinear function (normally called the 'activation function').

![The same as the previous figure, except that a row of pink circles labeled 'Non-Linear Transformation Layer' has been added in between the two hidden layers.](https://developers.google.com/machine-learning/crash-course/images/activation.svg)

You can add as many hidden layers and nodes within them as you see fit but it will alter the resource intensity of the NN, etc, etc.

## Forward Pass Example

![[Screenshot 2023-05-03 at 9.26.51 am.png]]

## [[Backpropagation (Gradient Flow)]]

#### Pause. Gimme some common nonlinear functions (activation functions) please.

Sure man but tbh you don't need to memorise these, tensorflow or whatever you're using has them built in, handy to know what's occuring behind the scenes though.

- ##### Sigmoid
Converts weighted sum to a val. between 0 and 1.
$$F(x) = \frac{1}{1+e^{-x}}$$

- ##### ReLU (Rectified Linear Unit)
Often a little better than a smooth func. like a sigmoid whilst being easier to compute.
$$F(x) = max(0,x)$$

- ##### Parametric ReLU

- ##### ELU

- ##### Maxout

### Practical Neural Network

Let's have a play: [Google ML Crash Course: NN Playground Exercise](https://developers.google.com/machine-learning/crash-course/introduction-to-neural-networks/playground-exercises)

## [[A Practical Recipe for Developing Neural Networks]]



See also:
- [[Machine Learning]]
- [Google ML Crash Course: Intro to Neural Network Anatomy](https://developers.google.com/machine-learning/crash-course/introduction-to-neural-networks/anatomy)
- [[Backpropagation (Gradient Flow)]]
- [Google Colab: Introd to Neural Nets](https://colab.research.google.com/github/google/eng-edu/blob/main/ml/cc/exercises/intro_to_neural_nets.ipynb?utm_source=mlcc&utm_campaign=colab-external&utm_medium=referral&utm_content=intro_to_nn_tf2-colab&hl=en)
- [NN Manifolds Topology Blog Post](https://colah.github.io/posts/2014-03-NN-Manifolds-Topology/)
- ['Why Neural Networks can learn (almost) anything' - Emergent Garden](https://www.youtube.com/watch?v=0QczhVg5HaI)