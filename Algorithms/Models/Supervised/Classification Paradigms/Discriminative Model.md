Models $P(Y|X)$ directly. Unlike [Generative Model](Algorithms/Models/Supervised/Classification%20Paradigms/Generative%20Model.md), do not learn the distributions of the inputs.

Instead, model the likelihood of getting this outcome given the observation.

Intuitively, this means we are trying to learn something in the input space other than the nature of the inputs. For example, we can learn decision boundaries - it doesn't matter what the true input distributions are in this case.

Examples:
- [Logistic Regression](Algorithms/Models/Supervised/General/Logistic%20Regression.md). 
	- For classification - considering the "0.5" vertical line on the output sigmoid function in the input space, then you can consider this 0.5 as the decision boundary for binary classification, for which the assigned output probability being higher or lower than 0.5 indicates predicted class.