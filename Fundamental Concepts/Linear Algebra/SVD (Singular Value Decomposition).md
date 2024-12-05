A generalization of [Eigendecomposition](Fundamental%20Concepts/Linear%20Algebra/Eigendecomposition.md).

Let:
- $X \in \mathbb{R}^{n\times p}$
- $U \in \mathbb{C}^{n\times n}$, $U$ is [Unitary](Fundamental%20Concepts/Linear%20Algebra/Unitary.md)
- $\Sigma\in \mathbb{R}^{n\times p}$, $\Sigma$ is diagonal and nonnegative
- $V \in \mathbb{C}^{p\times p}$, $V$ is [Unitary](Fundamental%20Concepts/Linear%20Algebra/Unitary.md)
Implying:
- $XX^{*} \in \mathbb{R}^{n\times n}$, known as the left [Gram Matrix](Fundamental%20Concepts/Linear%20Algebra/Gram%20Matrix.md) of $X$
- $X^{*}X \in \mathbb{R}^{p\times p}$, known as the right [Gram Matrix](Fundamental%20Concepts/Linear%20Algebra/Gram%20Matrix.md) of $X$

SVD is the task of decomposing matrix $X$ into matrices $U$, $\Sigma$, $V^T$ satisfying:
$$X=U\Sigma V^T$$
where:
- $U$ is the horizontal stacking of the $n$ length-$n$ **left singular vectors** of $X$, $\left[ u_0|u_1|...|u_{n-1}\right]$
	- **Left singular vectors** are the **eigenvectors** of $XX^{*}$. They might be complex-valued.
- $\Sigma$ is the diagonal matrix of the $\min(n,p)$ or fewer **singular values**, which are each denoted $\sigma$.
	- **Singular values** are the square roots of the **eigenvalues** of $XX^{*}$ (or of $X^{*}X$; they are equal)
- $V$ is the horizontal stacking of the $p$ length-$p$ **right singular vectors** of $X$, $\left[ v_0|v_1|...|v_{p-1}\right]$
	- **Right singular vectors** are the **eigenvectors** of $X^{*}X$. They might be complex-valued.
(recall that any square matrix $XX^{*}$ or $X^{*}X$ has $n$ eigenvectors and $n$ eigenvalues, not necessarily distinct)

# Derivation

To get the SVD, you just need an algorithm for calculating eigenvectors and eigenvalues (there are many options for this).

The intuitive expression which leads us to this conclusion is:
$$XV=U\Sigma$$
In other words, multiplying the right singular vectors by $X$ is equivalent to multiplying each left singular vector by its corresponding singular value:
$$Xv=\sigma u$$
This defines **singular values** - $\sigma$ is a singular value if there exist unit-norm vectors $u$ and $v$ satisfying the above. Those $u$ and $v$ are then the singular vectors.

# Usage

SVD is typically used for [PCA (Principal Components Analysis)](Algorithms/Models/Clustering/PCA%20(Principal%20Components%20Analysis).md). 

In PCA, interpret:
- Right singular vectors in columns of $V$ as the **principal axes** (since $V$ is unitary, these are known to be orthonormal).
- Squared singular values $\sigma^2$ as the amount of variation captured in the corresponding principal axis
- Left singular vectors in columns of $U$ as the **scores**, or the projections of the samples onto each principal axis. The columns after the $p$-th column would explain no variance.
- Define $P = XV = U\Sigma$ as the principal components decomposition.

In **low-rank approximation**, we take just the $k$ largest singular values and set the others to zero to approximate $X$ as the rank-$k$ $\tilde{X}$. ($k < n$ and $k < p$)

For **dimensionality reduction**, we cut out entire columns of each matrix. Let:
- $U_k\in \mathbb{C}^{n\times k}$ is the left $k$ columns of $U$
- $\Sigma_k\in \mathbb{C}^{k\times k}$ is the first $k$ rows and columns of $\Sigma$
- $V_k\in \mathbb{C}^{p\times k}$ is the left $k$ columns of $V$
Then:
$$P_k = XV_k=U_k\Sigma_k$$
**i.e. $V_k$ is the transformation matrix from original data $X$ to reduced-dimensions $P_k$.**

SVD is more numerically stable than [Eigendecomposition](Fundamental%20Concepts/Linear%20Algebra/Eigendecomposition.md), so it's preferred for PCA.


SVD can also be used for **diagonalization** - see [Eigendecomposition](Fundamental%20Concepts/Linear%20Algebra/Eigendecomposition.md).


SVD is not unique. #Q why?


