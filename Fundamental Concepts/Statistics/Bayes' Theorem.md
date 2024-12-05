$$P(A|B) = \frac{P(B|A)P(A)}{P(B)}$$
Intuitively: Update $P(A)$ with knowledge $B$, yielding new estimate $P(A|B)$.
This is always true, and this can be shown geometrically.
There are names for each term:

$P(A)$ is the "**prior**" probability. 
- It's the initial guess of $A$'s probability before knowing $B$ is true.
$P(A|B)$ is the "**posterior**" probability.
- It's the updated guess of $A$'s probability after knowing $B$ is true.

$P(B)$ is the "**marginal**" probability. 
- Effectively the size of the entire given space $B$.

$P(B|A)$ is the "**likelihood**". 
- This is the Bayesian definition of likelihood.
- This is probably made more intuitive in the context of a model.
	- Let $A$ define a model's parameters, like $\theta$.
	- Let $B$ define observations, like $X$.
	- Now Bayes' rule is:
	- $$P(\theta|X) = \frac{P(X|\theta)P(\theta)}{P(X)}$$
	- Then likelihood becomes $P(X|\theta)$, i.e. the probability of seeing this data under this model.
		- And we started with a certain guess for the model's probability $P(\theta)$, as well as the data's probability of occurring? #Q
	- We use the likelihood to update $P(\theta|X)$, i.e. the probability of this model's parameters being correct given the data.



