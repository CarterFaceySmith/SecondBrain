Using only FC layers to build an architecture is impractical since it is close to brute-force and there’s a lot of weights that need to be trained:

- $[3, 5, 5]$ image and 3 neuron in FC, 75x3 weights need to be trained 
- iImage sizes are 1k x 1k then we have 3 billion weights

Also there’s no structure, optimisation becomes hard and the performance drops.

Instead use a different structure: layer with structure, weight sharing (share the same weights for different parts of the image)

## Convolutions

An application of a *filter* to a function.

Given an 5x5 image, we use this filter to augment the value of each cell in that 5x5 in some way, different function yield different results, and these are typically called [[Filter Kernel]]s.

### RGB Images

For these, the depth of the image must match the depth of the filter, e.g. 3 for an RGB image, one output is then created for every convolution: $z_i=w^Tx_i+b_i$ where $w^T$ and $X_i$ are the size (width * height * depth) x 1.

## Convolutional Layers

In a convolution layer we can apply many filters with different weights, so we can have many activation maps → form a Convolution Layer. So a basic layer would be {filter width, filter height, number of different filter banks}.  

Each filter captures a different characteristic such as: edges, circles, squares, etc.

Imagine the convolutional layer as a tiny detective with a magnifying glass, scanning over an image. This detective is looking for specific features in the image, like edges, corners, or textures. The magnifying glass is like the filter or kernel, which is a small matrix of numbers. 

As the detective moves the magnifying glass across the image, it calculates a dot product between the values in the filter and the pixel values in the image. This process forms a new image, which is a map of where the filter found a match in the image. The cool part is that these filters are not pre-defined; they are learned by the network during training!

### Dimensions of a Convolutional Layer

$N$: Input width/height 
$F$: Filter/Kernel size 
$S$: Stride  
$P$: Padding

#### *Stride*
- Is the jump the filter does while sliding • Output is: (N−F +1)×(N−F +1)
- Fractions are illegal (Filter must not be outside the image partly). So check the stride. 

#### *Padding*
- Since the sizes get too small too quickly, we use padding. Also like this we can use the corner pixels more than once.
- Pad the whole picture with numbers (mostly zeros) around
- Output: $([\frac{N+2\cdot P-F}{S}]+1)\times([\frac{N+2\cdot P-F}{S}]+1)$ 
- Different paddings:
	- Valid: no padding
	- Same: output size = input size, set $P=\frac{F-1}{2}$

## CNN Pooling

Next up is the pooling layer, which is like the network's way of squinting. When you squint at something, you lose detail, but you also get a broader view. That's what the pooling layer does. It slides over the image and picks the biggest number from a patch in the previous layer (if we're using max pooling), effectively reducing the size of the image. This helps to make the network more efficient and less prone to overfitting.

Used as a downsampling layer. It picks the strongest activation in a region. Pooling layer goes directly after a convolution layer:

- Conv Layer = ‘Feature Extraction’: Computes a feature in a given region  
- Pooling Layer = ‘Feature Selection’: Picks the strongest activation in a region

![[Screenshot 2023-06-26 at 2.22.48 pm.png]]

Various pooling types:  
• Max Pooling  
• Average Pooling  
• Global Average Pooling

To finalise the CNN we add an FC layer (One or two FC layers typically).

## [[Receptive Field]]

## [[Batch Normalisation (BN)]] for CNN

We compute minibatch mean and variance for each channel C. 

Spatial batch norm: Compute mean and variance of each channel.

## Dropout for CNN

Standard: randomly drop a unit with a certain probability. This does not improve performance in CNN. 

Spatial: randomly sets entire feature maps to zero.

All of this brings us to the overall concept... 

## ***[[Transfer Learning]]***