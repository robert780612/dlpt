---
description: Some popular convolutional model
---

# Image recognition

## Network in network (NIN)

https://arxiv.org/abs/1312.4400
* Global average pooling
* 1*1 convolutional kernel

## Very Deep Convolutional Networks for Large-Scale Image Recognition (VGG)

https://arxiv.org/abs/1409.1556

* Simply stacks more convolution layers
* Stack small convolutional kernels to achieve the same "receptive field" as bigger one.
  * Stack two 3*3 convolutional kernel is equivalent to 5*5 convolutional kernel 

<figure class="image">
<img src=".gitbook/assets/receptive-field.png">
<figcaption>One 5*5 kernel and stacks two 3*3 kernels have the same effective receptive field.</figcaption>
</figure>

## Deep Residual Learning for Image Recognition (Resnet)

https://arxiv.org/abs/1512.03385

* Add residual connection
 
## Inception

## Xception

## Dense net

## Squeeze and excitation network

## Dual path network

## Shuffle network

## Squeeze network

## ResXt

## Fully Convolutional Attention Networks for Fine-Grained Recognition

https://arxiv.org/pdf/1603.06765.pdf

## Residual Attention Network for Image Classification

https://arxiv.org/pdf/1704.06904.pdf

https://github.com/tengshaofeng/ResidualAttentionNetwork-pytorch
https://github.com/youansheng/AttentionModule

