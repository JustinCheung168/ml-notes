

1. Candidate Mention Detection
	1. Identify all possible 
		1. Excess culling causes recall to go down.
		2. Excess inclusion causes precision to go down.
	2. Could use POS tagging, chunking, and/or NER
	3. State of art: train single neural model to jointly detect candidate mentions AND resolve them.
2. Clustering (aka Merging, aka Resolution)
	1. Create training data
		1. Can make positive examples from true antecedent/anaphor pairings, and negative by using other pairs that are entities.
			1. Start from anaphor and look left until finding an antecedent that is best.
			2. Or, use "Mentioned Rank" where instead of pairwise, make probability distribution over all possible antecedents, including no . 
			3. Neural approach in End-to-end neural coreference resolution paper. Embed first, last, and most important word; create mention and antecedent scores; calculate coreference scores; apply softmax.
	2. Mentioned Pair Detection
		1. 


"anaphora" is a reference to an entity that was previously introduced in the discourse. The referring expression is an "anaphor", and the thing it refers to is the "antecedent". so often a pronoun would be an anaphor. Anaphors don't always have an antecedent, sometimes it's implied like in "I heard it rained". A "singleton" is an entity with only one mention; you wouldn't call this an antecedent.


"coreference chain" is one set of mentions which corefer to the same entity. for example {Victoria Chen, her, the 38-year-old, She}

Challenge case: "Winograd Schema Problems". Where there are two parties to the event and a pronoun which could syntactically refer to either ambiguously, and some other word that if changed will change which thing the pronoun it refers to.
They're included in both GLUE and SuperGLUE.
