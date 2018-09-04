---
plugins:
  - katex
---

# Image style transfer

## A Neural Algorithm of Artistic Style

[https://www.cv-foundation.org/openaccess/content\_cvpr\_2016/papers/Gatys\_Image\_Style\_Transfer\_CVPR\_2016\_paper.pdf](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf)

[https://harishnarayanan.org/writing/artistic-style-transfer](https://harishnarayanan.org/writing/artistic-style-transfer)

[https://medium.com/artists-and-machine-intelligence/neural-artistic-style-transfer-a-comprehensive-look-f54d8649c199](https://medium.com/artists-and-machine-intelligence/neural-artistic-style-transfer-a-comprehensive-look-f54d8649c199)

### What is style?

If two images are the same in the view of style, they have the same correlation matrix of feature maps.

For example, feature A represents a hole structure and feature B represents a stripe texture. If both images are the same style \(stripe hole\), they appear in the both images at the same time, so the correlation matrix of features of the two images are the same.

### Algorithm

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

[https://en.wikipedia.org/wiki/Gramian\_matrix](https://en.wikipedia.org/wiki/Gramian_matrix)

## Perceptual Losses for Real-Time Style Transfer and Super-Resolution

[https://cs.stanford.edu/people/jcjohns/papers/eccv16/JohnsonECCV16.pdf](https://cs.stanford.edu/people/jcjohns/papers/eccv16/JohnsonECCV16.pdf)

