The sigmoid function is: 
$$\sigma(z)=\frac{1}{1+e^{-z}}$$
Note that it maps $\mathbb{R} \rightarrow [0,1]$.

The logistic regressor plugs the [Linear Regression](Algorithms/Models/Supervised/General/Linear%20Regression.md) function $w \cdot x + b$ in for $z$.

This is used as a binary classifier. The output would be interpreted as the model's output probability estimates for the positive class.

There is no known closed-form equation which computes the $w$ , so we use [Gradient Descent](Algorithms/Training/Iterative%20Optimization%20Techniques/Gradient%20Descent.md) instead.



### Multinomial Logistic Regressor

To make a multinomial logistic regressor, just replace sigmoid with softmax.
The softmax function generalizes the sigmoid function.
$$\text{softmax}(z_k) = \frac{e^{z_k}}{\sum_{j=1}^Ke^{z_j}}$$
Here's how the softmax collapses to sigmoid when there are two classes $1,2$; arbitrarily consider $1$ as the positive class, and let $z=z_1-z_2$:
$\text{softmax}(z_1) = \frac{e^{z_1}}{e^{z_1}+e^{z_2}} = \frac{e^{z_1}}{e^{z_1}+e^{z_2}}\frac{e^{-z_2}}{e^{-z_2}} = \frac{e^{z_1-z_2}}{e^{z_1-z_2}+e^{z_2-z_2}} = \frac{e^{z}}{e^{z}+1}\frac{e^{-z}}{e^{-z}} = \frac{1}{1+e^{-z}} = \sigma(z)$

Since softmax is of form $\frac{f(k)}{\sum_{j=1}^Kf(j)}$, such that across all $k \in \{1..K\}$, the sum $\sum_{k=1}^K\text{softmax}(z_k)$ is 1 (trivial to observe). Therefore it guarantees that the sum across classes is 1, making the output a true set of probabilities of the partition of classes.

And since it uses the exponentials, it still retains a sigmoid-like nature where it maps $\mathbb{R} \rightarrow [0,1]$ to allow this interpretation as probability, while also having a smooth gradient allowing smooth convergence on gradient descent and easy backpropagation calculation. 