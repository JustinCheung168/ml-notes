Also known as **Negative Log-Likelihood**.

### BCE
Binary Cross-Entropy.

Used for binary classification.
$$L_{CE}(\hat{y},y)=-\frac{1}{N}\sum_{i=1}^Ny^{(i)}\log(\hat{y}^{(i)})+(1-y^{(i)})\log(1-\hat{y}^{(i)})$$
This is the negated sum of the model's predicted log-likelihoods for each correct classification.

The formula masks to just the correct classifications by multiplying log-likelihoods by the true labels.

Intuitively, the model should be guessing that each correct classification is very likely.

The usage of negative log-likelihoods (i.e. curve that is positive infinity at 0, trails down towards 1) implies that predicting the correct class with low probability gets highly penalized.


### Multinomial Cross-Entropy

$\hat{y}_k^{(i)}$ is the model's estimated probability that observation i belongs to class $k$.
$y_k^{(i)}$ is the true "probability" that observation $i$ belongs to class $k$ - 1 if it does, 0 if it belongs to any other class. 
This is really just a more general expression of BCE, and could directly be used in that case too.

$$L_{CE}(\hat{y},y)=-\frac{1}{N}\sum_{i=1}^N\sum_{k=1}^Ky_k^{(i)}\log(\hat{y}_k^{(i)})$$
