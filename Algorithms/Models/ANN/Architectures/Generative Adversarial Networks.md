GAN

Two components:
- Generator
	- Tries to generate data that looks like the training data.
- Discriminator
	- Tries to classify real vs. fake data.

This is part of the fields of [Generative Learning](Algorithms/Models/ANN/Architectures/Generative%20Learning.md).

Its learning paradigm is called [Adversarial Training](Algorithms/Models/ANN/Architectures/Adversarial%20Training.md).

The generator is akin to how the decoder component of a [Variational Autoencoder](Algorithms/Models/ANN/Architectures/Variational%20Autoencoder.md) works, in the sense that it learns how to transform Gaussian noise into the training distribution. Like in the decoder, the Gaussian noise is then interpreted as codings for the image to be generated.
Unlike the decoder, the training procedure is quite different.

---
# Fit
The training of a GAN occurs in 2 phases:
1. Discriminator training
	1. Take a batch consisting of equal numbers of:
		- Real images (label 1)
		- Fake images (label 0), created by the generator.
	2. Use the discriminator to predict.
	3. Train just the discriminator on the batch using binary [CE (Cross-Entropy)](Algorithms/Training/Loss%20Functions/CE%20(Cross-Entropy).md) for 1 step via backpropagation. 
1. Generator training
	1. Take a batch consisting only of fake images. Mislabel them as 1.
	2. Use the discriminator to predict.
	3. Train the generator via backpropagation.
		- The gradients flow back from discriminator (whose weights are frozen) all the way back to the generator (whose weights are NOT frozen), based on how well the generator was able to make the discriminator mispredict the images.


GAN training is tricky due to "mode collapse", the problem where outputs become less diverse. For example, outputting only one image class that it's already good at will encourage the model to only provide that class. Even if it moves on to something else, it might focus on that and forget how to do the other class.

GANs are also very sensitive to hyperparameters, because of the complex dynamics incurred by how the two separate networks are pushing against each other.

"Experience replay" is a technique for helping with overfitting here, where fake images from past iterations are included alongside the new ones.

"Mini-batch discrimination" measures similarity across generated images and causes the discriminator to reject a whole batch of fake images that lacks diversity.

Check [DCGAN (Deep Convolutional GAN)](Algorithms/Models/ANN/Architectures/DCGAN%20(Deep%20Convolutional%20GAN).md) for tricks used to make more stable deep GANs.

"Progressive growing" is a technique from a 2018 Nvidia paper where later larger layers are gradually introduced.

"Minibatch standard deviation" at the end of the discriminator generates one more feature map for each instance which is uniformly the standard deviation of all channels and all instances in the batch. This lets the discriminator see diversity.

"Equalized learning rate" - weights are scaled down every time a layer is executed by a factor of $\sqrt{2/n_{inputs\_to\_the\_layer}}$ , same as in He initialization. i.e. instead of just initializing to scaled Gaussian distributed weights, the weights are repeatedly scaled, forcing same dynamic range for all parameters. (otherwise, those with a larger dynamic range take longer to train than those with a small dynamic range which update too quickly)

"Pixelwise normalization layer" - after every convolutional layer in the generator, normalize each activation that is at the same pixel location across channels.

---
# Implementation

A simple GAN can essentially just be a [Sequential](Algorithms/Models/ANN/Components/Sequential.md) model of the generator (which, again, is like an [Autoencoder](Algorithms/Models/ANN/Architectures/Autoencoder.md)'s decoder) followed by the discriminator (which is just any typical binary classification model; can just use an [MLP (Multilayer Perceptron)](Algorithms/Models/ANN/Architectures/MLP%20(Multilayer%20Perceptron).md) for example). 