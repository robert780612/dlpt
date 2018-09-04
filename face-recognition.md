---
plugins:
  - katex
---

# Face recognition

## Learning a Similarity Metric Discriminatively, with Application to Face Verification \(Siamese network\)

[http://yann.lecun.com/exdb/publis/pdf/chopra-05.pdf](http://yann.lecun.com/exdb/publis/pdf/chopra-05.pdf)

Training a similarity metric from data

## DeepFace: Closing the Gap to Human-Level Performance in Face Verification

[https://research.fb.com/wp-content/uploads/2016/11/deepface-closing-the-gap-to-human-level-performance-in-face-verification.pdf](https://research.fb.com/wp-content/uploads/2016/11/deepface-closing-the-gap-to-human-level-performance-in-face-verification.pdf?)

## FaceNet: A Unified Embedding for Face Recognition and Clustering

[https://arxiv.org/abs/1503.03832](https://arxiv.org/abs/1503.03832)


$$
||f(A^{(i)})-f(P^{(i)})||_2^2 + \alpha \lt ||f(A^{(i)})-f(N^{(i)})||_2^2
$$



$$
\text{Triplet loss}= \Big[||f(A^{(i)})-f(P^{(i)})||_2^2 - ||f(A^{(i)})-f(N^{(i)})||_2^2 + \alpha \Big]_+
$$


$$A^{(i)}$$ : anchor of i-th triplet, $$P^{(i)}$$: positive example of i-th triplet, $$N^{(i)}$$: negative example of i-th triplet, $$\alpha$$: margin

