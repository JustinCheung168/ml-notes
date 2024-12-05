The chain rule in statistics expands on the definition of [Conditional Probability](Fundamental%20Concepts/Statistics/Conditional%20Probability.md):
$$P(w_{1},w_{2},...,w_{n}) = P(w_{1})P(w_{2}|w_{1})P(w_{3}|w_{1}, w_{2})...P(w_{n}|w_{1}...w_{n-1})$$
or in short:
$$P(w_{1},w_{2},...,w_{n}) = \prod_{i=1}^{n}P(w_{i}|w_{1},...,w_{i-1})$$

This is useful in the formulation of some [LM (Language Model)](Tasks/NLP/Language%20Models/LM%20(Language%20Model).md)s.

# Markov Assumption

The $k$-th Order Markov Assumption simplifies the chain rule by assuming that only the previous $k$ terms of history (in addition to the current term) matter. 

In NLP, it yields a $(k+1)$-gram [LM (Language Model)](Tasks/NLP/Language%20Models/LM%20(Language%20Model).md).

For example, the 0th Order Markov Assumption yields a Unigram LM.

The general formula is:
$$P(w_{1},w_{2},...,w_{n}) = \prod_{i=k+1}^{n}P(w_{i}|w_{i-k},...,w_{i-1})$$

So for example, the zeroth order (i.e. no memory) is:
$$P(w_{1},w_{2},...,w_{n}) = \prod_{i=1}^{n}P(w_{i})$$

and the second order is:
So for example, the zeroth order (i.e. no memory) is:
$$P(w_{1},w_{2},...,w_{n}) = \prod_{i=3}^{n}P(w_{i}|w_{i-2},w_{i-1})$$