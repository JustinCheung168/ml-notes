Maximum Likelihood Estimate.

Goal is to find the model that maximizes the likelihood of observed training data.

This requires taking the model's likelihood function (i.e. its [PDF (Probability Density Function)](Fundamental%20Concepts/Statistics/PDF%20(Probability%20Density%20Function).md)) and calculating the joint probability of the observations given this model. Usually, assume the observations are independent - then this is just the product of probabilities of each observation using the model's PDF.

The MLE solution can be found analytically or iteratively. Iterative is needed where a closed-form solution doesn't exist.

Examples:
- [Logistic Regression](Algorithms/Models/Supervised/General/Logistic%20Regression.md)
- [NBC (](Algorithms/Models/Supervised/General/NBC%20(.md)
- 