# Image style transfer

## A Neural Algorithm of Artistic Style

[https://www.cv-foundation.org/openaccess/content\_cvpr\_2016/papers/Gatys\_Image\_Style\_Transfer\_CVPR\_2016\_paper.pdf](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf)

{% embed data="{\"url\":\"https://harishnarayanan.org/writing/artistic-style-transfer/\",\"type\":\"link\",\"title\":\"Convolutional neural networks for artistic style transfer — Harish Narayanan\",\"description\":\"There’s an amazing app out right now called Prisma that transforms your photos into works of art using the styles of famous artwork and motifs. The app performs this style transfer with the help of a branch of machine learning called convolutional neural networks. In this article we’re going to take a journey through the world of convolutional neural networks from theory to practice, as we systematically reproduce Prisma’s core visual effect.\",\"icon\":{\"type\":\"icon\",\"url\":\"https://harishnarayanan.org/icon.png\",\"aspectRatio\":0}}" %}

{% embed data="{\"url\":\"https://medium.com/artists-and-machine-intelligence/neural-artistic-style-transfer-a-comprehensive-look-f54d8649c199\",\"type\":\"link\",\"title\":\"Neural Artistic Style Transfer: A Comprehensive Look\",\"description\":\"Spring Quarter of my freshman year, I took Stanford’s CS 231n course on Convolutional Neural Networks. My final project for the course…\",\"icon\":{\"type\":\"icon\",\"url\":\"https://cdn-images-1.medium.com/fit/c/304/304/1\*dHo9DKqsmip4Hrfj9kUUog.jpeg\",\"width\":152,\"height\":152,\"aspectRatio\":1},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://cdn-images-1.medium.com/max/2000/1\*QvtiHFX8nicTD6A5SQx10Q.png\",\"width\":1238,\"height\":1226,\"aspectRatio\":0.9903069466882067},\"caption\":\"Explain NST with a Pytorch implement\"}" %}

Neural style transfer needs two images, one called content image \(C\) and another called style image \(S\). Our goal is produce an pastiche image \(P\) which content is kept as possible as C with style S.

Now, we define the loss function $$L_{total}$$ which contains two parts, the first one called the content loss \($$L_{content}$$\) measures how far is the pastiche \(P\) to the content image \(C\) in content, and the second part called the style loss \($$L_{style}$$\) measures how far is the pastiche image \(P\) to the style image \(S\) in style. Those losses are then minimized by directly changing the pastiche image.

$$
L_{total}=\alpha L_{content}(C,P)+\beta L_{style}(S,P)
$$

The content loss, measured the content difference between content image \(C\) and the predicted image \(P\), is the Frobenius norm of the difference of the activation value in a specific layer.

$$
L_{content}(C,P)=||A^{[l](C)}-A^{[l](P)}||^2
$$

The style loss, measured the style difference between style image \(S\) and the predicted image \(P\), is the summation of the weighted \($$w_l$$\) Frobenius norm of the difference gram matrix over all layers.

$$
L_{style}(S,P)=\sum_{l=1}^{L}w_l||G^{[l](S)}-G^{[l](P)}||^2
$$

The gram matrix of the l-th layer of data x is denoted as $$G^{[l](x)}$$. And the element of the i-th row and the j-th column is the inner product of the i-th activated feature map and the j-th activated feature map. 

$$
G^{[l](x)}=\begin{bmatrix}
<A^{[l](x)}_{i},A^{[l](x)}_{j}>
\end{bmatrix}
$$

Inner product measures the distance between these two vectors \(cosine similarity without divided by length\). If two unit vectors tend to similar, they would get higher inner product value.

{% embed data="{\"url\":\"https://en.wikipedia.org/wiki/Gramian\_matrix\",\"type\":\"link\",\"title\":\"Gramian matrix\",\"description\":\"In linear algebra, the Gram matrix \(Gramian matrix or Gramian\) of a set of vectors \\n  \\n    \\n      \\n        \\n          v\\n          \\n            1\\n          \\n        \\n        ,\\n        &\#x2026;\\n        ,\\n        \\n          v\\n          \\n            n\\n          \\n        \\n      \\n    \\n    {\\\\displaystyle v\_{1},\\\\dots ,v\_{n}}\\n  \\n in an inner product space is the Hermitian matrix of inner products, whose entries are given by \\n  \\n    \\n      \\n        \\n          G\\n          \\n            i\\n            j\\n          \\n        \\n        =\\n        &\#x27E8;\\n        \\n          v\\n          \\n            i\\n          \\n        \\n        ,\\n        \\n          v\\n          \\n            j\\n          \\n        \\n        &\#x27E9;\\n      \\n    \\n    {\\\\displaystyle G\_{ij}=\\\\langle v\_{i},v\_{j}\\\\rangle }\\n  \\n.&\#91;1&\#93;\\n\",\"icon\":{\"type\":\"icon\",\"url\":\"https://en.wikipedia.org/static/apple-touch/wikipedia.png\",\"aspectRatio\":0}}" %}

## Perceptual Losses for Real-Time Style Transfer and Super-Resolution

[https://cs.stanford.edu/people/jcjohns/papers/eccv16/JohnsonECCV16.pdf](https://cs.stanford.edu/people/jcjohns/papers/eccv16/JohnsonECCV16.pdf)

