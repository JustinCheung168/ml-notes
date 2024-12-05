A language model typically for [Sequence Labeling](Tasks/NLP/Tasks/Sequence%20Labeling.md) following this rule on sequence words $w_i$ and their corresponding classes $c_i$:
$$P(w_k|w_{1:k-1})=P(w_k|c_k)P(c_k|c_{1:k-1})$$
Typically simplified with this assumption:
$$P(w_k|w_{1:k-1})=P(w_k|c_k)P(c_k|c_{k-1})$$



