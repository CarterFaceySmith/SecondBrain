Receptive field is the size of the region in the input space that a pixel in the output space is affected by; the spatial extent of the connectivity of a convolutional filter. What is the relationship between the input and the output? 

For example: 3x3 receptive field: 1 output pixel is connected to 9 input pixels.

Used in [[Convolutional Neural Networks (CNN)]].

For FC layers, the receptive field is the ***ENTIRE*** image. Since each output neuron of that layer is connected to each neuron of the previous one, where each layer represents the entire output, whether it is downscaled or upscaled.