I'll use notation inspired by [Linear Regression](Algorithms/Models/Supervised/General/Linear%20Regression.md). 

- $X\in \mathbb{R}^{n\times p}$ is the standard expression for a real matrix with $n$ rows and $p$ columns.
	- Its typical interpretation is that $X$ is the **feature matrix** of $n$ observations, each of which have $p$ features.
- $\mathbf{y}\in \mathbb{R}^n$ is the standard expression for a real vector with $n$ rows. Vectors are assumed by default to be column vectors.
	- Its typical interpretation is that $\mathbf{y}$ is the **target vector** of $n$ observations.
- $\boldsymbol{\beta}\in \mathbb{R}^p$ is the standard expression for a real vector of $p$ coefficients typically considered to be constant.
	- Its typical interpretation is that $\boldsymbol{\beta}$ is a set of **regression coefficients** for the features.

This is not typical notation, this is just a little easier to remember for me. 

However, it does confuse some inherent meaning - whereas in linear algebra we usually think of $X$ as a transformation matrix for $\boldsymbol{\beta}$ to become $\mathbf{y}$ (i.e. input vector becomes output vector), in linear regression $\boldsymbol{\beta}$ instead parametrizes the transformation of $X$ to become $\mathbf{y}$ (i.e. input matrix becomes output vector).

Nevertheless, the notation will be used to help tie into concepts for usage in machine learning.



