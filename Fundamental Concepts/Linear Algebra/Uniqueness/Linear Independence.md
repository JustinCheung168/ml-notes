Let:
- $X\in \mathbb{R}^{n\times p}$
	- $X$ is the standard matrix for transformation $T: \mathbb{R}^p \rightarrow \mathbb{R}^n$
- $\boldsymbol{\beta}\in \mathbb{R}^p$
- $\boldsymbol{0}_n\in \mathbb{R}^n$
- $\boldsymbol{0}_p\in \mathbb{R}^p$

The following statements are all equivalent:
- The columns of $X$ are **linearly independent**
- $X\boldsymbol{\beta}=\textbf{0}_n$ only has the trivial solution $\mathbf{0}_p$ (this defines linear independence)
- $T$ is [Into](Fundamental%20Concepts/Linear%20Algebra/Uniqueness/Into.md)
- The [Image](Fundamental%20Concepts/Linear%20Algebra/Existence/Image.md) $\text{Image}(T)=\mathbb{R}^m$ 

The intuitive expression of this is to say that none of the column vectors can be formed as a linear combination of the other column vectors.

Another expression is this: the set of vectors $\{\mathbf{x}_0, \mathbf{x}_1,...\mathbf{x}_{n-1}\}$ are linearly independent iff the only solution of the following equation is the trivial solution $\beta_i=0\ \forall \ i\in\{0..n-1\}$:
$$\sum_{i=0}^{n-1} c_i \mathbf{x}_i$$
where all $c_i$ are scalars.

This is equivalent to saying that none of the vectors can be formed as a linear combination of the others.

Its dual is [Span](Fundamental%20Concepts/Linear%20Algebra/Existence/Span.md).
