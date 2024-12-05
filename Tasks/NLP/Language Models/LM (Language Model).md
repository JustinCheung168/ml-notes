A statistical language model is a statistical distribution over words.
(or symbols or characters)

Examples of questions it might answer:
- How likely is a provided sequence?
	- i.e. what is $P(w_{1},w_{2},...,w_{n})$?
- How likely is a given completion of a sequence?
	- i.e. what is $P(w_{n}|w_{n-1},w_{n-2},...,w_{1})$?

It's usually easiest to find either of these by applying the [Chain Rule](Fundamental%20Concepts/Statistics/Chain%20Rule.md).



