An [Encoder](Algorithms/Models/ANN/Architectures/Encoder.md)-only model based on

Looks at entire sentence at once.

Uses transformers to make a contextual language model.

Transformers look at entire input at once (they are not recurrent)
Use positional embeddings to track input position
Gets power from multiple "attention" layers.
Easily parallelized.

Every token gets a vector (not every )