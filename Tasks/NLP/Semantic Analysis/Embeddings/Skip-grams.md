One of two word2vec models, the other being [CBOW (Continuous Bag of Words)](Tasks/NLP/Semantic%20Analysis/Embeddings/CBOW%20(Continuous%20Bag%20of%20Words).md), which it is sort of the reverse paradigm of.
Typically better than [CBOW (Continuous Bag of Words)](Tasks/NLP/Semantic%20Analysis/Embeddings/CBOW%20(Continuous%20Bag%20of%20Words).md).

Predict context words given target word.



Input: V-dimensional one-hot vector representing target word

Output: set of V-dimensional probability distributions for words that co-occur with target word.


Train, then retain W.




