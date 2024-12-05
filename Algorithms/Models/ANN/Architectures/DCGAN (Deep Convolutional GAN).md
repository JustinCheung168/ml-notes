2015

Came as result of a lot of experimentation in architectures and hyperparameters. 
The tricks for stable convolutional GANs was:
- Replace pooling with strided convolutions in the discriminator, and transposed convolutions in the generator.
- Batch normalization and most layers except where the generator and discriminator meet.
- Remove fully connected hidden layers for deeper architectures.
- ReLU for generator layers except output which is tanh; leaky ReLU for all discriminator layers.

Interestingly, the coding layer representations can have some vector arithmetic done with them - for example, "man with glasses" minus "man without glasses" plus "woman without glasses" yields "woman with glasses"


