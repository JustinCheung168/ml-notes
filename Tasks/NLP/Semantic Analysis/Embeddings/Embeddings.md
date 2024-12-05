Dense vector representations of words.
Usually chosen to express something about **semantics**, but can also be chosen to express **structure** as well.

Two major types:
- **Static** embedding
	- Every word maps to exactly 1 embedding.
	- This lets the embeddings be quite portable.
	- However, the multiple possible meanings of a word are hard to capture this way.
- **Contextual** embedding
	- Every word instance 

Methods of generating: 
- Static embeddings:
	- Word2Vec
		- [CBOW (Continuous Bag of Words)](Tasks/NLP/Semantic%20Analysis/Embeddings/CBOW%20(Continuous%20Bag%20of%20Words).md)
		- [Skip-grams](Tasks/NLP/Semantic%20Analysis/Embeddings/Skip-grams.md)
	- [GloVe (Global Vectors for Word Representation)](Tasks/NLP/Semantic%20Analysis/Embeddings/GloVe%20(Global%20Vectors%20for%20Word%20Representation).md)
	- [fastText](Tasks/NLP/Semantic%20Analysis/Embeddings/fastText.md)
- Contextual embeddings:
- [PCA (Principal Components Analysis)](Algorithms/Models/Clustering/PCA%20(Principal%20Components%20Analysis).md)
- [Encoder](Algorithms/Models/ANN/Architectures/Encoder.md) networks
- etc.
Note that several of these are pretty similar, because embedding generation is similar to dimensionality reduction.




Can form analogies as vectors represent certain relationships.

Vector from man to woman is similar to vector from king to queen.

King - man + woman is similar to queen.




Window size C in their generation is a parameter that can determine choice.

C=2 might relate syntactically similar things, C=5 might relate semantically related words.



Algorithms like conditional random fields may benefit from discrete embeddings rather than 