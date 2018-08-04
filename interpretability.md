---
description: This page collect some papers which try to interpret the neural network.
---

# Interpretability

## Visualizing and Understanding Convolutional Networks

[https://cs.nyu.edu/~fergus/papers/zeilerECCV2014.pdf](https://cs.nyu.edu/~fergus/papers/zeilerECCV2014.pdf)

## Learning Deep Features for Discriminative Localization \(Class activation mapping, CAM\)

{% embed data="{\"url\":\"https://arxiv.org/abs/1512.04150\",\"type\":\"link\",\"title\":\"\[1512.04150\] Learning Deep Features for Discriminative Localization\",\"icon\":{\"type\":\"icon\",\"url\":\"https://arxiv.org/favicon.ico\",\"aspectRatio\":0}}" %}

Class activation mapping \(CAM\)

* A weakly supervised localization method.
* If the last three layers are "convolution + global average pooling+ full connection\), then you can apply this method to visualize object location.
* Just use fc's weight and calculate weighted sum of convolution feature maps \(without global average pooling\).

![Class activation mapping](.gitbook/assets/cam.png)

