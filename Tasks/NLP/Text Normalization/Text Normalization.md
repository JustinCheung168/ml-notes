The task of putting text into some convenient standardized format that is usable as input to other NLP operations.

Must run quickly.

Examples include:
- [Tokenization](Tasks/NLP/Text%20Normalization/Tokenization.md)
- [Lemmatization](Tasks/NLP/Text%20Normalization/Lemmatization.md)
- [Case Folding](Tasks/NLP/Text%20Normalization/Case%20Folding.md)
- [Sentence Boundary Detection](Tasks/NLP/Text%20Normalization/Sentence%20Boundary%20Detection.md)
- Expanding [Clitic](Fundamental%20Concepts/Linguistics/Clitic.md) contractions

May be tied up with

	- Two possible strategies:
		- #Top-Down #Tokenization: Define a standard and implement rules accordingly.
		- #Bottom-Up #Tokenization: Start from elements, which we call #SubwordTokens/def , and derive rules from them.
- #BPE/def
	- Byte pair encoding algorithm.
	- A form of #Bottom-Up #Tokenization.
- #PennTreebank/def
	- Penn Treebank tokenization is a standard for #Top-Down #Tokenization. 
- #Lemmatization/def
	- Task of determining that two words have the same root (lemma) **semantically**.
	- example:
		- sang, sung, sings are the #Wordform 's which map to the #Lemma sing.
	- Complex approaches need to implement #MorphologicalParsing/def, the **structural** breakdown of a word into #Morpheme 's.
	- One technique is #Stemming
- #Stemming/def
	- Simple version of #Lemmatization in which we just strip suffixes from the end of the word.
	- Common technique: the #PorterAlgorithm/def, a series of rewrite rules run in series. 
	- Could be used to collapse across different variants of the same lemma.
	- Otherwise rarely used now - commits errors of over-generalizing (policy becomes police) and under-generalizing (European does not become Europe)
- #SentenceSegmentation/def
	- Task of splitting up sentences. 
- #CaseFolding/def
	- The simplest case of word normalization.
- #MinimumEditDistance/def
	- The minimum number of edits (such as insertions, deletions, and substitutions) needed to transform one string to another.
		- The cost of each of insertions, deletions, and substitutions is up to you and can be parameters for #MinimumEditDistanceAlgorithm .
	- Calculated via the #MinimumEditDistanceAlgorithm/def, invented independently by many.
		- This is a dynamic programming algorithm using a 2D array where rows are one word and columns are another.

