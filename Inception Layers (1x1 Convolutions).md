Inception layers are a smart way of performing convolutions with multiple [[Filter Kernel]] (Filter) sizes on the same level. Instead of choosing whether your convolutions are going to be 1x1, 3x3, or 5x5, why not use all of them and let the network decide what's best?

## 1x1? What's the fuck?

1x1 convolutions, also known as pointwise convolutions, might seem a bit weird at first. I mean, a 1x1 filter? Really? But hear me out, they're actually pretty useful.

1x1 convolutions are used to change the dimensionality of the feature maps. If you have a lot of feature maps (say, 192 of them), and you want to reduce that number to make your network more computationally efficient, you can use 1x1 convolutions. For example, using 64 1x1 convolutions on 192 28x28 feature maps would give you 64 28x28 feature maps. It's like a [[Dimensionality-Reduction]] technique, but for your feature maps.

## Why are they useful?

1x1 convolutions are a way of doing channel-wise pooling. Instead of pooling over the spatial dimensions (height and width) like in max pooling or average pooling, you're pooling over the channels. This can help to reduce the number of parameters in your network, making it more efficient.

Inception layers, on the other hand, allow the network to learn different features at different scales. By using multiple filter sizes at the same level, the network can learn to recognise patterns of *various* sizes.
