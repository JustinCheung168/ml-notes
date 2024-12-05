Also (strangely) called "Batch Gradient Descent" (as opposed to [Mini-Batch Gradient Descent](Algorithms/Training/Iterative%20Optimization%20Techniques/Mini-Batch%20Gradient%20Descent.md) or [SGD (Stochastic Gradient Descent)](Algorithms/Training/Iterative%20Optimization%20Techniques/SGD%20(Stochastic%20Gradient%20Descent).md))

Approach for dealing with optimization on a function's contour when the function is unknown. Evaluation of this function (such as a loss function) is typically expensive, so it's impossible to take the derivative.

Traditional formulation to perform gradient descent on loss $L(\hat{y},y)$:
$\theta_{t+1} = \theta_t-\eta\nabla L(f(x;\theta),y)$

i.e. Update the weights $\theta$ by calculating the gradient of the loss function.

Sufficiently simple models have easy gradient calculations:

- Example gradient calculation for [MSE (Mean Squared Error)](Algorithms/Training/Loss%20Functions/MSE%20(Mean%20Squared%20Error).md).
![](Screenshots/GeronEquation4-6.png)
- Example gradient calculation for Binary [CE (Cross-Entropy)](Algorithms/Training/Loss%20Functions/CE%20(Cross-Entropy).md):
![](Screenshots/JurafskyMartinEquation5-29.png)