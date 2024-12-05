Linking entity mentions to a knowledge base.

Two phases:
1. Candidate Identifiation (aka Triage)
	1. Quickly determine from Knowledge Base and entity mention in context which knowledge nodes contain the entity. Must use a fast strategy, like string matching or acronym matching
2. Candidate Ranking
	1. Match mentioned string against each candidate. Often uses supervised learning techniques. Includes a NIL option if the named entity is not in the knowledge base.
