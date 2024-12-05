A task which applies [Sequence Labeling](Tasks/NLP/Tasks/Sequence%20Labeling.md).

It imposes extra rules on the labels:
- The labels are in the form of:
	- For each class:
		- B-CLASS
		- I-CLASS
	- O

where B- represents the first word of a given entity, I- represents any other words in the same entity as the previous B- tag, and O represents any other word.

In an [HMM (Hidden Markov Model)](Algorithms/Models/Supervised/General/HMM%20(Hidden%20Markov%20Model).md) solution, you block off paths that would not be allowed under this interpretation (namely, you can never start with an I- tag, and you can never go directly from O to an I- tag; see the red arrows):
![](Tasks/NLP/Tasks/HMM_NER_ValidRoutes.png)



