# Image style transfer

## A Neural Algorithm of Artistic Style

[https://www.cv-foundation.org/openaccess/content\_cvpr\_2016/papers/Gatys\_Image\_Style\_Transfer\_CVPR\_2016\_paper.pdf](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf)

{% embed data="{\"url\":\"https://harishnarayanan.org/writing/artistic-style-transfer/\",\"type\":\"link\",\"title\":\"Convolutional neural networks for artistic style transfer — Harish Narayanan\",\"description\":\"There’s an amazing app out right now called Prisma that transforms your photos into works of art using the styles of famous artwork and motifs. The app performs this style transfer with the help of a branch of machine learning called convolutional neural networks. In this article we’re going to take a journey through the world of convolutional neural networks from theory to practice, as we systematically reproduce Prisma’s core visual effect.\",\"icon\":{\"type\":\"icon\",\"url\":\"https://harishnarayanan.org/icon.png\",\"aspectRatio\":0}}" %}

{% embed data="{\"url\":\"https://medium.com/artists-and-machine-intelligence/neural-artistic-style-transfer-a-comprehensive-look-f54d8649c199\",\"type\":\"link\",\"title\":\"Neural Artistic Style Transfer: A Comprehensive Look\",\"description\":\"Spring Quarter of my freshman year, I took Stanford’s CS 231n course on Convolutional Neural Networks. My final project for the course…\",\"icon\":{\"type\":\"icon\",\"url\":\"https://cdn-images-1.medium.com/fit/c/304/304/1\*dHo9DKqsmip4Hrfj9kUUog.jpeg\",\"width\":152,\"height\":152,\"aspectRatio\":1},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://cdn-images-1.medium.com/max/2000/1\*QvtiHFX8nicTD6A5SQx10Q.png\",\"width\":1238,\"height\":1226,\"aspectRatio\":0.9903069466882067},\"caption\":\"A Pytorch implement\"}" %}

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

$$
G^{[l](x)}=\begin{bmatrix}
<A^{[l](x)}_{i},A^{[l](x)}_{j}>
\end{bmatrix}
$$



