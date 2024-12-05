Also known as **add-one smoothing**.

It's just adding one count to each possible event in a probability distribution.

# NLP

Seldom used in practice for NLP, but it's an easy approach to handle unseen data.

$$P_{smoothed}(x_i|x_{i-1}) = \frac{c(x_{i-1},x_i)+1}{c(x_{i-1})+V}$$

