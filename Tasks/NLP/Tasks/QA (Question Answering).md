Slightly more specific than [IR (Information Retrieval)](Tasks/NLP/Tasks/IR%20(Information%20Retrieval).md) and might also involve IR as a part of the process.

Taxonomies of question types can vary. 
Li and Roth proposed based on answer types:
- Abbreviation
- Description
- Entity
- Human
- Location
- Numeric
Graesser & Pereson proposed based on question type (16 types), ranging from objective true/false all the way to making a judgement on something or what causes led to an effect.

Examples of complexity:
- How many astronauts walked on the moon? - probably can use regex to extract 1 number
- Name astronauts who have walked on the moon. - might need to look at multiple documents
- What Russian spacecraft first flew around the moon? - might need reasoning about what a spacecraft is and then what first is
- When was the first lunar colony established? - needs to know to report nothing.
- Tell me about the Apollo program - need an implicit understanding of the request.
- What were its major hurdles? - need to resolve reference and metaphor and abstract concepts
- Why is China now pursuing a manned lunar mission? - need cause/effect

The BASEBALL interface attempted to fit a question into one of the known schema, then do database lookup.

Early systems were "closed domain" - i.e. only going to be about one domain.
"Open domain" is harder but a lot of systems do that now

TREC was a series of evaluations that ran for about 8 years from 1999. Considered 3 genres of questions:
- Factoid - return a noun phrase
- List - return a list with no duplicates
- Definition - return a set of fields, some mandatory and some optional

# Approaches to Factoid QA

- Regex likely won't cut it.
- Pre-neural [IR (Information Retrieval)](Tasks/NLP/Tasks/IR%20(Information%20Retrieval).md) approach (called a retrieval approach, since search is a big part of the problem)
	- Question Processing
	- Docuemnt and Passage Retrieval
	- Answer Type Detection
	- ![](Tasks/NLP/Tasks/QA%20pipeline.png)