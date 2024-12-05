KL divergence loss targets a specific level of sparsity. This is considered better for this task than MAE or MSE.

Let:
- $P$ - discrete probability distribution
- $Q$ - discrete probability distribution

KL divergence is defined as:
$$D_{KL}(P\Vert Q)=\sum_iP(i)\log{\frac{P(i)}{Q(i)}}$$

In the [Autoencoder](Algorithms/Models/ANN/Architectures/Autoencoder.md) training context, interpreting as $p$ being target probability that a neuron in the coding layer will activate, and the actual probability $q$ which is the mean activation over the training batch, this simplifies to:
$$D_{KL}(p\Vert q)=p\log{\frac{p}{q}} + (1-p)\log{\frac{1-p}{1-q}}$$


