One of two word2vec models, the other being [Skip-grams](Tasks/NLP/Semantic%20Analysis/Embeddings/Skip-grams.md).

Use contexts to predict a word.

Input: A set of V-dimensional one-hot vectors representing contexts.

Connect input to hidden using V x N matrix W.

Hidden: N-dimensional vector representing average of vectors of input words.

Connect hidden to output using N x V matrix C.

Output: V-dimensional probability distribution over vocabulary words.



