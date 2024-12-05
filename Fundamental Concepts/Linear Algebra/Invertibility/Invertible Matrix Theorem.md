Let:
- $X\in \mathbb{R}^{n\times n}$
	- $X$ is the standard matrix for transformation $T: \mathbb{R}^n \rightarrow \mathbb{R}^n$

The Invertible Matrix Theorem states that for a square $X$, all of the following are equivalent statements:
1. $X$ is invertible
2. $T$ is invertible
3. $\exists X^{-1}$ s.t. $XX^{-1}=X^{-1}X=I$ (this is what defines an **invertible matrix**)
5. The rows of $X$ have [Linear Independence](Fundamental%20Concepts/Linear%20Algebra/Uniqueness/Linear%20Independence.md).
6. The rows of $X$ [Span](Fundamental%20Concepts/Linear%20Algebra/Existence/Span.md) $\mathbb{R}$.
7. $\det(X) \neq 0$
8. $0$ is not an eigenvalue $\lambda$ of $X$.
9. The row reduction of $X$ is $I$
10. The columns of $X$ form a basis for $\mathbb{R}^n$
11. $X^T$ is invertible
12. The columns of $X$ have [Linear Independence](Fundamental%20Concepts/Linear%20Algebra/Uniqueness/Linear%20Independence.md).
13. The columns of $X$ [Span](Fundamental%20Concepts/Linear%20Algebra/Existence/Span.md) $\mathbb{R}^n$.
**All of the implications of [Linear Independence](Fundamental%20Concepts/Linear%20Algebra/Uniqueness/Linear%20Independence.md) and [Span](Fundamental%20Concepts/Linear%20Algebra/Existence/Span.md) also follow.**
