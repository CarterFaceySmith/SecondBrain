Generative means the network/model is able to generate new data instances, put simply this network makes new shit from old shit.

### The structure of a GAN

![[Screenshot 2023-07-23 at 12.30.14 pm.png]]

This is a two parter:
1. The generator: learns how to generate plausible data, this data becomes negative training examples for the discriminator; and
2. The discriminator: learns how to distinguish the generator's fake data from real data, penalises the generator for producing implausible results.

You can see how running both results in a cycle of exponentially improving data until the real is no longer distinguishable from the fake and the cycle stops.

Both parts are [[Neural Networks (NN)]], with the generator output being directly connected to the discriminator input. [[Backpropagation (Gradient Flow)]] is used to send a signal from the discriminator's classification to the generator that is used to update it's weights.

### The Discriminator (discrim. cos it's a long fkn word)

What a name lol.

Simply a classifier, it can use any network architecture appropriate for the type of data it's classifying.

*It's a learnable [[Loss Function]].

#### Training one

The discrim. connects two [[Loss Function]]s, during training the generator loss is ignored and only discrim. loss is used.

First, the discrim. classifies both real and fake data from the generator.

Then, discrim. loss penalises the discrim. for misclassifying (giving a false pos. or neg. either way).

Finally, the discrim. updates it's weights through [[Backpropagation (Gradient Flow)]] from the discrim. loss through the discrim. network.

### The Generator

Basically learns to make the discrim. classify it's output as real.

#### Training one

The recipe for a good generator:
1. random input (at it's most basic it takes in random noise);
2. generator network, transforms the rand. input into a data instance;
3. discrim. network to classify the generated data;
4. discrim. output; and
5. generator loss, to penalise the generator for failing to fool the discrim.

##### Using the discrim. to train the generator the traditional way (missionary sex generator training)

1. sample random noise;
2. produce generator ouput from sampled random noise;
3. get discrim. real and fake classifications;
4. calculate loss from discrim. classification;
5. [[Backpropagation (Gradient Flow)]] through both the discrim. and generator to obtain gradients; and
6. use gradients to change only the generators weights.

### But can we train the GAN as a whole?

Yes, using alternating training.

> GAN training proceeds in alternating periods:
> 1.  The discriminator trains for one or more epochs.
> 2.  The generator trains for one or more epochs.
> 3.  Repeat steps 1 and 2 to continue to train the generator and discriminator networks.

We keep that generator constant during the discrim. training phase and as the discrim. tries to figure out what the fuck is fake and real it learns to recognise the generators flaws. Ofc we keep the discrim. constant during the generator training phase.

This back and forth is what develops the network. As the generator improves with training, the discrim. performance gets worse until the convergence occurs (the point where the real and fake data are indistinguishable bb).

### [[GAN Loss Functions]]

See also:
- 

