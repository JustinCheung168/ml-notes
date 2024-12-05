Linking entity mentions of the same entity to each other across documents (not to a knowledge base as in [Entity Linking](Tasks/NLP/Tasks/Entity%20Linking.md))

Step after [Within-Document Coreference Resolution](Tasks/NLP/Tasks/Within-Document%20Coreference%20Resolution.md). Depends heavily on high-quality performance in that step, otherwise get a lot of noise.

May use clustering, like agglomerative clustering of the coreference chains, or divisive clustering starting from all together and splitting out chains.

Kripke system is a rule-based system asked to do cold-start building of a knowledge base. Unsupervised clustering technique.
Principles of Kripke:
1. need good matching of names and contextual features to combine clusters.
2. a small set of discriminating contextual feautres is enough for disambiguoation.
Avoids quadratic time of brute force pairwise comparison by keeping inverted index of names used for each entity. Only entities matching by full name or by some shared words/n-grams are considered. Only surrounding words are considered for the comparison. Sums normalized IDF of intersection of rarest 10 co-occurring entities. So specific terms like Enrico Castelli are more important for discrimination than Rick. 

NLP tasks typically start at untrained, then go to learning rules, then full machine learning. But Kripke shows that fully untrained is still useful.