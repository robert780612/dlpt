# Transposed convolution

## Adaptive Deconvolutional Networks for Mid and High Level Feature Learning

[http://www.matthewzeiler.com/wp-content/uploads/2017/07/iccv2011.pdf](http://www.matthewzeiler.com/wp-content/uploads/2017/07/iccv2011.pdf)

**Transposed convolution = Fractional strided convolution**


### Explain what is deconvolution (transposed convolution, a learnable upsampling)

Transposed convolution just recovers the **shape** of the origin image, but don't **value**.

Consider the first layer of model, the c-th channel of input \($$y_1^c$$\), it could be reconstructed by convolving the first layer output which contains$$K_1$$channels \($$z_{k,1}, k=1,...,K_1$$\) with the filter \($$f^c_{k,1}$$\).

$$
\hat{y}_1^c=\sum_{k=1}^{K_1} z_{k,1}*f_{k,1}^c
$$

And any convolution can be represented as matrix multiplication

$$
\hat{y}_1 = F_1 z_1
$$

A reconstruct operator $$R_l$$ compose a sequence convolutional matrix and upsampling matrix, which $$\hat{y}_l$$ is the reconstructing image from the l layer feature map.

$$
\hat{y}_l=F_1U_{s1}F_2U_{s2}...F_lz_l=R_lz_l
$$

Hence, the projection operator $$R^T_l$$ maps the input image to $$z_l$$

$$
R^T_l=F_l^T...P_{s2}F_2^TP_{s1}F_1^T
$$

{% hint style="danger" %}
The projection operator is not in the sense of vector project. It more likes recover the shape to input space.
{% endhint %}

{% hint style="danger" %}
$$F^T$$ and $$F$$ are not the transposed relationship in the matrix meaning. The weights of these two operators are trained separately.
{% endhint %}

## A guide to convolution arithmetic for deep learning

[https://arxiv.org/pdf/1603.07285.pdf](https://arxiv.org/pdf/1603.07285.pdf)

