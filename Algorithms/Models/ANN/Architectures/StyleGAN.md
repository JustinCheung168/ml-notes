


"Style transfer" in generator ensures generated images have measurably similar local structure as the training images at every scale.

The generator has two parts:
- "Mapping network" is an 8-layer MLP which maps codings to multiple style vecttors. The style vectors come from affine transformation, controlling style features at multiple scales like fine-grained texture like hair to high-level like adult vs. child.
- "Synthesis network" processes a constant input which was determined from learning by adding noise and to all convolution layer outputs, then standardizes each feature map independently within itself, then uses the style vector to govern where to finally scale and offset it to.
 The generator architecture:
 ![](Algorithms/Models/ANN/Architectures/StyleGAN%20generator.png)