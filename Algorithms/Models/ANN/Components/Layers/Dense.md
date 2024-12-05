# Theory

A Dense layer is a vector of hidden features $\mathbf{h}$ is given by:
$\mathbf{h} = \phi(\mathbf{W^{\mathsf{T}}}\mathbf{x})$

where assuming $\mathbf{h}$ is length-$n_h$, $\mathbf{x}$ is size-$p$ and $\mathbf{W}$ is $p\times n_h$ .

Consider how this is a set of [Neuron](Algorithms/Models/ANN/Components/Neuron.md)s (each of which is a scalar) defined like this:
$h = \phi(\mathbf{w}^\mathsf{T}\mathbf{x})$

Given all of the inputs or a mini-batch of inputs as $\mathbf{X}$ (which would be $n\times p$), all the features $\mathbf{H}$ can be calculated at once as:
$\mathbf{H} = \phi(\mathbf{XW})$

(for whatever, reason, in Geron the Dense layer is notated as if a function without a specific name for the output matrix, as):
$h_{\mathbf{W}}(\mathbf{x}) = \phi(\mathbf{XW})$

In general, think of a "layer" as a new set of hidden features - so each neuron is a feature (and you could think of the input neurons as their own [Input](Algorithms/Models/ANN/Components/Layers/Input.md) layer).

In something like Keras, the calculations required to get to this layer from the previous layers is implied by whatever the shapes of the layers themselves need.

Note that it's implied that bias terms are included. 

In the below example (which has 2 Dense layers), it's probably easiest to think of one layer as the neurons and whatever is needed to calculate them.

![](Screenshots/GeronFigure10-7.png)
Note that the bias terms are 


# Keras
https://keras.io/api/layers/core_layers/dense/
Most basic layer of an [MLP (Multilayer Perceptron)](Algorithms/Models/ANN/Architectures/MLP%20(Multilayer%20Perceptron).md).






.