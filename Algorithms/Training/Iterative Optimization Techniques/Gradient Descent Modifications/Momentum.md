[Gradient Descent](Algorithms/Training/Iterative%20Optimization%20Techniques/Gradient%20Descent.md) is:
$\theta_{t+1} = \theta_t-\eta\nabla L(f(x;\theta_t),y)$
Gradient Descent with momentum $v_t$ is:
$\theta_{t+1} = \theta_t-\eta\nabla L(f(x;\theta_t),y) + \gamma v_t$
	($v_0=0, \theta_0=0$)
Gradient Descent with Nesterov momentum is:
$\theta_{t+1} = \theta_t-\eta\nabla L(f(x;\theta_t+v_t),y) + \gamma v_t$
	(the $\theta_t+v_t$ term represents where you would be if you followed momentum)
