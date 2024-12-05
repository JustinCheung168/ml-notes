
Learns dense representations.

The idea is for the output to try to recreate the input, but under conditions like limiting the dense representation size in the middle of the network, or adding noise to the inputs.

Two components:
- Encoder
	- Converts the inputs to a latent representation
- Decoder
	- Converts the latent representation to the outputs (often called "reconstructions")

The latent representation will be more efficient because it is of lower dimensionality. This property makes us consider autoencoders as "undercomplete".

Similar to a [MLP (Multilayer Perceptron)](Algorithms/Models/ANN/Architectures/MLP%20(Multilayer%20Perceptron).md), but requiring that the number of outputs equal to the number of inputs.

The loss function in this case is called "reconstruction loss", penalizing when the reconstruction differs from the original.



---
# As PCA

Interestingly, if the activations are purely linear and the cost function is [MSE (Mean Squared Error)](Algorithms/Training/Loss%20Functions/MSE%20(Mean%20Squared%20Error).md), then the autoencoder performs a kind of [PCA (Principal Components Analysis)](Algorithms/Models/Clustering/PCA%20(Principal%20Components%20Analysis).md).

Let:
- $X \in \mathbb{R}^{n\times p}$
- $U \in \mathbb{C}^{n\times n}$, $U$ is [Unitary](Fundamental%20Concepts/Linear%20Algebra/Unitary.md)
	- $U_k\in \mathbb{C}^{n\times k}$ is the left $k$ columns of $U$
- $\Sigma\in \mathbb{R}^{n\times p}$, $\Sigma$ is diagonal and nonnegative
	- $\Sigma_k\in \mathbb{C}^{k\times k}$ is the first $k$ rows and columns of $\Sigma$
- $V \in \mathbb{C}^{p\times p}$, $V$ is [Unitary](Fundamental%20Concepts/Linear%20Algebra/Unitary.md)
	- $V_k\in \mathbb{C}^{p\times k}$ is the left $k$ columns of $V$
- $P\in \mathbb{C}^{n\times k}$

Due to linear activations, the encoder degenerates to a single weights matrix $V_k$ which under MSE loss ends up minimizing variance along directions in $V_k$ (proof?) , so the data in the latent space is $P=XV_k$.


---
# As dimensionality reduction

A trained autoencoder can be used for dimensionality reduction. 

For visualization, if the coding layer still has too many dimensions, you can just use something like [t-SNE (t-Distributed Stochastic Neighbor Embedding)](Algorithms/Models/Clustering/t-SNE%20(t-Distributed%20Stochastic%20Neighbor%20Embedding).md) after the first dimension reduction provided by the coding layer.

---

# As a denoiser

You can have noise added to the input and make the network try to predict the original input.