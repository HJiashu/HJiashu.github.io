---
layout: page
title: Spectral Tensor Layers
description:  for Communication-free Distributed Deep Learning
img: assets/img/publication_preview/Spectral_Networks.jpg
importance: 4
category: work
---
In this paper, we propose a novel spectral tensor layer for communication-free distributed deep learning. The overall framework is as follows: first, we represent the data in tensor form (instead of vector form) and replace the matrix product in conventional neural networks by tensor product, which in effect imposes certain transformed-induced structure on the original weight matrices, e.g., a block-circulant structure; then we apply a linear transform along a certain dimension to split the original dataset into multiple spectral sub-datasets; as a result, the proposed spectral tensor network consists of parallel branches where each branch is a conventional neural network trained on a spectral sub-dataset with ZERO communication cost. The parallel branches are directly ensembled (i.e., weighted sum of their outputs) to generate an overall network with substantially stronger generalization capability than that of each branch. Moreover, the proposed method enjoys a byproduct of decentralization gain in terms of memory and computation, compared with traditional networks. It is a natural yet elegant solution for heterogeneous data in federated learning, where data at different nodes have different resolutions. Finally, we evaluate the proposed spectral tensor networks on the MNIST, CIFAR-10, ImageNet-1K, and ImageNet-21K datasets,respectively, to verify that they simultaneously achieve communication-free distributed learning, distributed storage reduction, parallel computation speedup, and learning with multi-resolution data.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/publication_preview/Spectral_Networks.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Overview of the spectral layer.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/publication_preview/tnnls.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Achieves SOTA performance while decreasing GPU consumption by a large margin
</div>
