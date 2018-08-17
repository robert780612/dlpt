---
description: This page collect some papers which try to interpret the neural network.
---

# Interpretability

## Visualizing and Understanding Convolutional Networks

[https://cs.nyu.edu/~fergus/papers/zeilerECCV2014.pdf](https://cs.nyu.edu/~fergus/papers/zeilerECCV2014.pdf)

## Learning Deep Features for Discriminative Localization \(Class activation mapping, CAM\)

[http://cnnlocalization.csail.mit.edu/Zhou\_Learning\_Deep\_Features\_CVPR\_2016\_paper.pdf](http://cnnlocalization.csail.mit.edu/Zhou_Learning_Deep_Features_CVPR_2016_paper.pdf)

Class activation mapping \(CAM\)

* A weakly supervised localization method.
* If the last three layers are "convolution + global average pooling+ full connection\), then you can apply this method to visualize object location.
* Just use fc's weight and calculate weighted sum of convolution feature maps \(without global average pooling\).

![Class activation mapping](../.gitbook/assets/cam.png)

Let $$a_1,..., a_k$$ be the k feature maps of the last convolution layer and followed by GAP and FC layers, and $$M$$is the size of a feature map, and $$w_n $$ is the weight which connected n-th filter to one of the scores called "s".

$$
s = \sum_{n=1}^k (w_n \frac{\sum_{ij} (a_n)_{ij}}{M})=\frac{1}{M}\sum_{ij} (\sum_{n=1}^kw_na_n)_{ij}
$$

It changed the layers' order from "conv-&gt;GAP-&gt;FC" to "conv-&gt;FC-&gt;GAP". The following simple equation is called the "class activation mapping" of class "s**"**.

$$
\text{CAM}=\sum_{n=1}^kw_na_n
$$

