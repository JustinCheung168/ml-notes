The task of associating tokens with labels.

i.e. unlike [Text Classification](Tasks/NLP/Tasks/Text%20Classification.md) which we usually consider as classifying entire sentence or even documents, in sequence labeling we are trying to classify every word.

For example:
- **Part-of-speech tagging**.
- [NER (Named Entity Recognition)](Tasks/NLP/Tasks/NER%20(Named%20Entity%20Recognition).md)

Possible solutions:
- Statistical Sequence Labeling
	- [HMM (Hidden Markov Model)](Algorithms/Models/Supervised/General/HMM%20(Hidden%20Markov%20Model).md)
- Neural Sequence Labeling
	- [RNN (Recurrent Neural Network)](Algorithms/Models/ANN/Architectures/RNN/RNN%20(Recurrent%20Neural%20Network).md)
	- [LSTM (Long Short-Term Memory)](Algorithms/Models/ANN/Components/Layers/LSTM%20(Long%20Short-Term%20Memory).md)
	- [GRU (Gated Recurrent Unit)](Algorithms/Models/ANN/Components/Layers/GRU%20(Gated%20Recurrent%20Unit).md)
	- Typically pair LSTM or GRU with [CRF (Conditional Random Field)](Algorithms/Models/Supervised/General/CRF%20(Conditional%20Random%20Field).md)
		- e.g. [FLAIR SequenceTagger](Algorithms/Models/ANN/Architectures/RNN/FLAIR%20SequenceTagger.md)





