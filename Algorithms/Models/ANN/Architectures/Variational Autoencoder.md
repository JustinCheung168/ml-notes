An [Autoencoder](Algorithms/Models/ANN/Architectures/Autoencoder.md) where the dense coding that is usually output by the encoder is replaced by a random generator with learned parameters which act as the codings.

This means that it is still probabilistic even after training, and it can generate new instances that resemble samples from the training set.

For example, you may have mean coding $\boldsymbol{\mu}$ and standard deviation $\boldsymbol{\sigma}$ .
To achieve training that enforces that the network correctly lets these codings represent a Gaussian distribution in the hidden representation, we use [Latent Loss](Algorithms/Training/Loss%20Functions/Latent%20Loss.md).