A type of [[Neural Networks (NN)]] architecture.

![[Pasted image 20230626135308.png]]

Still based on fully connected layers with [[Activation Function]] layers.

Consists of:
1. Encoder, reduces the dimensionality towards a latent space which forces the network to learn only the most meaningful features from the data, reducing information loss.
2. Decoder, receives the reduced space and aims to reconstruct the input of the encoder, therefore the output has the same shape as the input.

For the [[Loss Function]], normally [[L1 Loss]] or the MSE ([[L2 Loss]]) between each pixel in the input and corresponding one in the output is used.

For the latent space, you need to find the right size.

## Why the fuck do we even want to use this, realistically?

Autoencoders are an excellent solution to a state where our dataset is very big, but only just a small part of it is actually labeled, like a medical CT dataset, for example, as you can infer the remainder quite well.