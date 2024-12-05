# Theory

## Blackbox
A single LSTM layer from a black-box perspective is conceptually this:
$\mathbf{y}_{(t)}, \mathbf{h}_{(t)} = f(\mathbf{x}, \mathbf{h}_{(t-1)})$

Compare/contrast to a single [Dense](Algorithms/Models/ANN/Components/Layers/Dense.md) layer:
$\mathbf{h} = f(\mathbf{x})$

Three main differences:
- The main one is the recurrence relation.
- The hidden representation $\mathbf{h}$ is conceptually different from the output representation $\mathbf{y}$. For an LSTM, $\mathbf{y}$ is the information you'll pass to the next layer (akin to the $\mathbf{h}$ in the Dense formulation), whereas the LSTM's $\mathbf{h}$ carries information between timesteps (no analogue in the Dense formulation).
	- Be careful - this $\mathbf{h}$ is not the same one I'll use in the whitebox formulation, it's just an abstraction of some hidden information that will be passed to the next timestep. Not sure why the notation is so overloaded...
- $f$ is implemented differently between the two (not a simple linear combination with activation in LSTM, but at the black box level this can be ignored. see whitebox for the full equations and the 8 weights matrices which replace the usual Dense weights matrix)

Often you'll see this "unrolled", so it'll look like there are multiple copies of the layer, but it's really just 1. In the context of "unrolling" the LSTM, a single timestep's instance of the LSTM layer is called an LSTM "cell". Note that generally the cell is always the same shape unrolled over time (there could be exceptions but that's not the normal formulation).
## Whitebox
![](Screenshots/GeronFigure15-9.png)
$\mathbf{c}$ is cell, representing the long-term state.
$\mathbf{h} = \mathbf{y}$ is hidden, representing the short-term state (and also the output).

The intermediate calculations are:

$\mathbf{g}$ is the cell candidate - analogous to the usual Dense output, but its important parts get modified using:
- $\mathbf{f}$ is forget gate control signal - used to **forget past long-term** memory.
- $\mathbf{i}$ is input gate control signal - used to add **current input** to long-term.
$\mathbf{o}$ is output gate controller - controls which parts of long-term state should go out as the short-term output.

The actual weights learned here are notated as:
$\mathbf{W}_{xi}$, $\mathbf{W}_{hi}$, $\mathbf{b}_i$
$\mathbf{W}_{xf}$, $\mathbf{W}_{hf}$, $\mathbf{b}_f$
$\mathbf{W}_{xo}$, $\mathbf{W}_{ho}$, $\mathbf{b}_o$
$\mathbf{W}_{xg}$, $\mathbf{W}_{hg}$, $\mathbf{b}_g$

i.e. there are approximately 8 times as many weights compared to a similarly-formulated Dense layer (a little bit less, when accounting for biases) - you account for both input and hidden weights, and you need weights for the cell candidate $\mathbf{g}$ and the three controllers.

The proper definitions are:
$\mathbf{i}_{(t)} = \sigma(\mathbf{W}_{xi}^{\mathsf{T}} \mathbf{x}_{(t)} + \mathbf{W}_{hi}^{\mathsf{T}} \mathbf{h}_{(t-1)})+\mathbf{b}_i$
$\mathbf{f}_{(t)} = \sigma(\mathbf{W}_{xf}^{\mathsf{T}} \mathbf{x}_{(t)} + \mathbf{W}_{hf}^{\mathsf{T}} \mathbf{h}_{(t-1)})+\mathbf{b}_f$
$\mathbf{o}_{(t)} = \sigma(\mathbf{W}_{xo}^{\mathsf{T}} \mathbf{x}_{(t)} + \mathbf{W}_{ho}^{\mathsf{T}} \mathbf{h}_{(t-1)})+\mathbf{b}_o$
$\mathbf{g}_{(t)} = \tanh(\mathbf{W}_{xg}^{\mathsf{T}} \mathbf{x}_{(t)} + \mathbf{W}_{hg}^{\mathsf{T}} \mathbf{h}_{(t-1)})+\mathbf{b}_g$
$\mathbf{c}_{(t)} = \mathbf{f}_{(t)} \odot \mathbf{c}_{(t-1)} + \mathbf{i}_{(t)} \odot \mathbf{g}_{(t)}$
$\mathbf{h}_{(t)} = \mathbf{o}_{(t)} \odot \tanh(\mathbf{c}_{(t)})$

Compare/contrast to [Dense](Algorithms/Models/ANN/Components/Layers/Dense.md), which only has its output:
$\mathbf{h} = \phi(\mathbf{W^{\mathsf{T}}}\mathbf{x})$

(recall that $\odot$ is elementwise multiplication, i.e. Hadamard product)

