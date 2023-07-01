Remember [[Transfer Learning]]? Yeah, training can be a pain in the ass if you have limited data and other resources, so we can use a pre-trained model and add our own classifier on top of it.

## OK, so what do RNNs do?

Recurrent Neural Networks, or RNNs, are a type of artificial [[Neural Networks (NN)]] designed for sequence prediction problems. Unlike traditional neural networks, which process inputs independently, RNNs have loops that allow information to be passed from one step in the sequence to the next.

## How do they work?

RNNs process sequences of inputs by maintaining a 'state' containing information about past elements in the sequence. This state is passed along from one step in the sequence to the next, allowing the network to incorporate information from the past when making predictions about the future.

## Why are they useful?

RNNs are particularly useful for tasks that involve sequential data, like language translation, speech recognition, and time series prediction. They're able to capture patterns in the input data that span different points in time, which can be really useful for these kinds of tasks.

## What's the deal with vanishing/exploding gradients?

Training RNNs can be a bit tricky due to the problem of vanishing and exploding gradients. This problem arises because the gradients that are calculated using [[Backpropagation (Gradient Flow)]] can grow very large or small, causing the weights to be updated in a way that's either too big or too small. This can make the network hard to train.

## What are some types of RNNs?

There are several types of RNNs that have been developed to address some of the issues with the basic RNN model. These include:

- [[Long Short-Term Memory (LSTM)]]: LSTMs have a more complex internal structure than standard RNNs, which helps them better capture long-term dependencies in the data.

- Gated Recurrent Unit (GRU): GRUs are a simplified version of LSTMs that perform similarly but are easier to compute.

- Bidirectional RNNs: These RNNs process the data in both directions (forward and backward), which can provide additional context for the predictions.