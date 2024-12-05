The task of selecting documents that would be considered relevant based on a query.

Three types:
- **Keyword Search** - Find all locations where a single term is explicitly found in a document collection.
- **Ad hoc Querying** - Given a single "information need" expressed by the user as input, find a ranked list of documents within a fixed collection where that information would likely be contained.
	- In other words - The query is a variable input, the document collection is fixed.
- **[Text Classification](Tasks/NLP/Tasks/Text%20Classification.md)** - Assuming a fixed "standing query" which we are always interested in, find documents 
	- In other words - The query is fixed, the document collection is a variable input.
	- Perform using supervised ML.