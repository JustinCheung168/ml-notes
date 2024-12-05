# Theory

Foundational building block of most [NN (Neural Networks)](Algorithms/Models/ANN/NN%20(Neural%20Networks).md).

This is a scalar representing 1 hidden feature $h$. I'll notate the weights which generate this specific feature as $\mathbf{w}$. So given input $\mathbf{x}$, we get a single hidden feature as:
$h = \phi(\mathbf{x}^\mathsf{T}\mathbf{w})$

For that reason, in Geron this is notated as $h_{\mathbf{w}}(\mathbf{x})$. It's one linear combination of its inputs $\mathbf{x}$ weighted by $\mathbf{w}$, followed by an activation function $\phi$:
$h_{\mathbf{w}}(\mathbf{x}) = \phi(\mathbf{x}^\mathsf{T}\mathbf{w})$

It represents a single hidden feature.

The simplest example is a Linear Threshold Unit (LTU), which can be thought of as a **function** transforming input to next output. This example uses a step function $\text{step}$ as the [Activation Function](Algorithms/Models/ANN/Activation%20Functions/Activation%20Function.md):
![](Screenshots/GeronFigure10-4.png)
So in this case, we have
$h_{\mathbf{w}}(\mathbf{x}) = \phi(\mathbf{x}^\mathsf{T}\mathbf{w})$
$= \phi(x_1w_1+x_2w_2+x_3w_3)$
where $\phi$ is $\text{step}$. 

Now look at how they are used in a [Dense](Algorithms/Models/ANN/Components/Layers/Dense.md) layer.


