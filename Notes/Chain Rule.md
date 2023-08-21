The chain rule is a fundamental rule of [[Calculus]] that tells us how to calculate the [[Derivative]] of a composition of functions. In the context of computer science, the chain rule is commonly used in [[Machine Learning]] and optimisation [[Algorithms]].

## Core Concept

Let's say we have two functions, $f(x)$ and $g(x)$, where $g(x)$ is a function of $f(x)$, which in turn is a function of $x$. In other words, $g(x)$ is the outer function and $f(x)$ is the inner function. We can represent this composition of functions as $g(f(x))$.

The chain rule tells us that the derivative of $g(f(x))$ with respect to $x$ is equal to the product of the derivative of $g$ with respect to $f(x)$ and the derivative of $f$ with respect to $x$. In mathematical notation, this can be written as:

$$(d/dx) g(f(x)) = (dg/df) * (df/dx)$$

This means that if we want to find the derivative of the composition of two functions, we can first find the derivative of the outer function with respect to the inner function, and then multiply it by the derivative of the inner function with respect to the input variable.

## Why the fuck does this matter?

In the context of machine learning, the chain rule is used to calculate [[Gradient Descent]] of the loss function with respect to the weights of [[Neural Networks (NN)]]. This allows us to update the weights of the network in the direction that minimizes the [[Loss Function]] and improves the performance of the network.