As you progress your [[Convolutional Neural Networks (CNN)]] you are adding more and more layers, training is becoming harder and you may face vanishing or exploding gradients.

In a typical CNN, each layer feeds into the next layer, right? But in a network with skip connections, the input to a layer is also added to the output of a layer located further down the network. 

Imagine you have a layer `L` and the next layer is `L+1`. Instead of just feeding the output of layer `L` into layer `L+1`, you also add the output of layer `L` to the output of layer `L+1`. It's like layer `L+1` is getting a "helping hand" from layer `L`.

## Why are they useful?

Skip connections help to address the vanishing gradient problem, which is when the gradient becomes too small and the network becomes tough to train. They allow the gradient to be directly computed via [[Backpropagation (Gradient Flow)]] to earlier layers.

They also help with the degradation problem, which is when the network accuracy gets saturated and then degrades rapidly with the network depth increasing. The degradation problem is not caused by overfitting and adding more layers to a suitably deep model leads to higher training error.

## Real-world Applications

Skip connections are used in many state-of-the-art CNN architectures, including ResNet, DenseNet, and more. They're a big deal in the world of deep learning, and have helped to achieve some pretty impressive results in image recognition tasks.