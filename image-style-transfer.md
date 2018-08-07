# Image style transfer

## A Neural Algorithm of Artistic Style

{% embed data="{\"url\":\"https://arxiv.org/abs/1508.06576\",\"type\":\"link\",\"title\":\"\[1508.06576\] A Neural Algorithm of Artistic Style\",\"icon\":{\"type\":\"icon\",\"url\":\"https://arxiv.org/favicon.ico\",\"aspectRatio\":0}}" %}

$$
L_{total}=\alpha L_{content}(C,P)+\beta L_{style}(S,P)
$$

The content loss, which is the Frobenius norm of the difference activation value in a specific layer, measure the content difference between content image \(C\) and predicted image \(P\).

$$
L_{content}(C,P)=||A^{[l](C)}-A^{[l](P)}||^2
$$

The style loss, which is the summation of the weighted Frobenius norm of the difference gram matrix over all layers, measure the style difference between style image \(S\) and predicted image \(P\).

$$
L_{style}(S,P)=\sum_{l=1}^{L}w_l||G^{[l](S)}-G^{[l](P)}||^2
$$

