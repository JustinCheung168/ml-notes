An **orthonormal matrix** has columns which are a set of unit-norm vectors which are all [Orthogonal](Fundamental%20Concepts/Linear%20Algebra/Orthogonal.md) to each other.
The complex version is [Unitary](Fundamental%20Concepts/Linear%20Algebra/Unitary.md).
Subset of [Normal](Fundamental%20Concepts/Linear%20Algebra/Normal.md) matrices.

Rotation matrices with no scaling or translation component are orthonormal matrices.

Let:
- $X\in \mathbb{R}^{n\times n}$

The following conditions are equivalent:
1. $X$ is orthonormal
2. $X$ preserves inner product - $\left<Xu,Xv\right>=\left<u,v\right>$
3. $X$ preserves norms - $\lVert Xu \rVert = \lVert u \rVert$
4. Columns of $X$ form an **orthonormal basis** for $\mathbb{R}^n$
5. $X^T=X^{-1}$
6. $X^TX=XX^T=I$
7. $X^T$ is orthonormal
8. $X^{-1}$ is orthonormal

