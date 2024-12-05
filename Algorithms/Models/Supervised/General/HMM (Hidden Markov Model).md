A statistical sequence labeling technique based on a Markov model, where the transition probabilities are learned from data.

Applied in [Sequence Labeling](Tasks/NLP/Tasks/Sequence%20Labeling.md).
Let's think of this in an NLP context.
In the directed graph structure of the Markov Model:
- Every class in the vocabulary is a node.
- The transition probability is calculated directly from the counts of each class label transitioning to each other class label in the training sequences.

The possible routes through an HMM can be expressed as a **"lattice"**.
![](Algorithms/Models/Supervised/General/Screenshot%202024-11-25%20at%204.24.19%20PM.png)

An efficient algorithm for finding the best labeling through the lattice is the **Viterbi Decoding algorithm**.




