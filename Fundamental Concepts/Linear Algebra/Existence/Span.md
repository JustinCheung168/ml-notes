Let:
- $X\in \mathbb{R}^{n\times p}$
	- $X$ is the standard matrix for transformation $T: \mathbb{R}^p \rightarrow \mathbb{R}^n$
- $\boldsymbol{\beta}\in \mathbb{R}^p$
- $\boldsymbol{y}\in \mathbb{R}^n$

The following statements are all equivalent:
- The columns of $X$ **span** $\mathbb{R}^p$
- $X\boldsymbol{\beta}=\textbf{y}$ is [Consistent](Fundamental%20Concepts/Linear%20Algebra/Consistent.md) (this defines span)
- $T$ is [Onto](Fundamental%20Concepts/Linear%20Algebra/Existence/Onto.md)
- The [Null Space](Fundamental%20Concepts/Linear%20Algebra/Uniqueness/Null%20Space.md) $\text{Ker}(T)=\{\mathbf{0}\}$

The intuitive expression of this is to say that the transformation expressed by $X$ can reach any possible output values of $\mathbf{y}$.

Its dual is [Linear Independence](Fundamental%20Concepts/Linear%20Algebra/Uniqueness/Linear%20Independence.md).
