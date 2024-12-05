
Let:
- $X\in \mathbb{R}^{n\times n}$
- $V\in \mathbb{R}^{n\times n}$
- $\Lambda\in \mathbb{R}^{n\times n}$, $\Lambda$ is diagonal
Implying:
- $V^{-1}\in \mathbb{R}^{n\times n}$

Eigendecomposition is the task of decomposing square matrix $X$ into matrices $V$, $\Lambda$, and $V^{-1}$:

$$X=V\Lambda V^{-1}$$
where:
- $V$ is the horizontal stacking of the $n$ length-$n$ eigenvectors of $X$, $\left[ v_0|v_1|...|v_{N-1}\right]$
- $\Lambda$ is the diagonal matrix of the $n$ eigenvalues
(recall that any square matrix $X$ has $n$ eigenvectors and $n$ eigenvalues, not necessarily distinct)

# Derivation

In other words, to get the eigendecomposition, you just need an algorithm for calculating eigenvectors and eigenvalues (there are many options for this).

The intuitive expression which leads us to this conclusion is:
$$XV=V\Lambda$$
In other words, multiplying the eigenvectors by $X$ is equivalent to multiplying each eigenvector by its corresponding eigenvalue.

# Usage

We can also say that matrix $X$ is **diagonalized** by eigenvectors $V$ into eigenvalues $\Lambda$, which is an easier matrix to compute with:
$$X = V\Lambda V^{-1}$$
For example:
$$X^{1000}=V\Lambda ^{1000} V^{-1}$$
This can be demonstrated easily by looking at how the $V$ and $V^{-1}$ cancel out:
$$X^{1000}=V\Lambda V^{-1} V\Lambda V^{-1}V\Lambda V^{-1}V\Lambda V^{-1}...$$

This is one of the major reasons to perform eigendecomposition, to find $V$ and $\Lambda$ to begin with.

# When does it work?

Not all square $X$ are diagonalizable. 
- If $X$ has all distinct eigenvalues, then it definitely works.
- Otherwise, the geometric multiplicities must match the algebraic multiplicities.

The generalization of eigendecomposition to rectangular matrices is [SVD (Singular Value Decomposition)](Fundamental%20Concepts/Linear%20Algebra/SVD%20(Singular%20Value%20Decomposition).md).


