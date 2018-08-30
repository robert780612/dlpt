---
description: NAS
---

# Neural architecture search

## Collections

{% embed data="{\"url\":\"https://www.ml4aad.org/automl/literature-on-neural-architecture-search/\",\"type\":\"link\",\"title\":\"Literature on Neural Architecture Search – AutoML\",\"icon\":{\"type\":\"icon\",\"url\":\"https://www.automl.org/wp-content/uploads/2018/07/automl\_org\_favi-1.png\",\"aspectRatio\":0}}" %}

## Neural Architecture Search: A Survey

[https://arxiv.org/pdf/1808.05377.pdf](https://arxiv.org/pdf/1808.05377.pdf)

1. Search space
   * Small search space reduces the size of search space
   * But introduces a human bias
   * Prevent finding novel architecture
2. Search strategy
   * How to explore the search space
3. Performance estimation strategy
   * The objectives of NAS is typically to find architectures that achieve high predictive performance on unseen data.

### Search space

Input of layer i can be formally described as a function: $$g_i(L_{i-1}^{out},...,L_{0}^{out})$$

* Chain-structured network: $$g_i(L_{i-1}^{out},...,L_{0}^{out})=L_{i-1}^{out}$$
* Residual type network: $$g_i(L_{i-1}^{out},...,L_{0}^{out})=L_{i-1}^{out}+L_{j}^{out}$$
* Dense connected network: $$g_i(L_{i-1}^{out},...,L_{0}^{out})=\text{concat}(L_{i-1}^{out},...,L_{0}^{out})$$

### Search strategy

* Random search
* Bayesian optimization
* Evolutionary methods
* Reinforcement learning
* Gradient based methods

### Performance estimation strategy

* Regular training
* Lower resolution image
* Less filter per layer

## Neural Architecture Search with Reinforcement Learning

[https://arxiv.org/pdf/1611.01578.pdf](https://arxiv.org/pdf/1611.01578.pdf)



