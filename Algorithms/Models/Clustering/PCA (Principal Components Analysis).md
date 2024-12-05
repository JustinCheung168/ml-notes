Let:
- $X_{train}\in \mathbb{R}^{n_{train}\times p}$
- $X_{test}\in \mathbb{R}^{n_{test}\times p}$
- $V\in \mathbb{R}^{p\times p}$
- $V_k\in \mathbb{R}^{p\times k}$, $k<p$
- $P_{test}\in \mathbb{R}^{n_{test}\times k}$

Before fitting or transforming, you MUST perform standard scaling of the data.

# Fit

See [SVD (Singular Value Decomposition)](Fundamental%20Concepts/Linear%20Algebra/SVD%20(Singular%20Value%20Decomposition).md).
The final "model" is $V_k$, which are the leftmost $k$ columns of right singular vectors (principal axes) $V$, which was derived from the SVD of $X_{train}$.

# Transform

Multiply new data $X_{test}$ by the $V_k$ derived from training data:
$P_{test} = X_{test}V_k$

$P_{test}$ is thus the low-dimensional representation of $X_{test}$.

