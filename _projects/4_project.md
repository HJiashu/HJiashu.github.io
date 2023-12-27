---
layout: page
title: Learned, Uncertainty-driven Adaptive Acquisition
description: for Photon-Efficient Multiphoton Microscopy
img: assets/img/publication_preview/fig_2_architecture.png
importance: 3
category: work
---
Multiphoton microscopy (MPM) is a powerful imaging tool that has been a critical enabler for live
tissue imaging. However, since most multiphoton microscopy platforms rely on point scanning,
there is an inherent trade-off between acquisition time, field of view (FOV), phototoxicity, and
image quality, often resulting in noisy measurements when fast, large FOV, and/or gentle imaging
is needed. Deep learning could be used to denoise multiphoton microscopy measurements, but
these algorithms can be prone to hallucination, which can be disastrous for medical and scientific
applications. We propose a method to simultaneously denoise and predict pixel-wise uncertainty
for multiphoton imaging measurements, improving algorithm trustworthiness and providing
statistical guarantees for the deep learning predictions. Furthermore, we propose to leverage this
learned, pixel-wise uncertainty to drive an adaptive acquisition technique that rescans only the
most uncertain regions of a sample. We demonstrate our method on experimental noisy MPM
measurements of human endometrium tissues, showing that we can maintain fine features and
outperform other denoising methods while predicting uncertainty at each pixel. Finally, with our
adaptive acquisition technique, we demonstrate a 120× reduction in acquisition time and total
light dose while successfully recovering fine features in the sample. We are the first to demonstrate
distribution-free uncertainty quantification for a denoising task with real experimental data and
the first to propose adaptive acquisition based on reconstruction uncertainty

<div class="row">
    <div class="col-sm mt-md-0">
        {% include figure.html path="assets/img/publication_preview/fig_1_summary.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    (a) Uncertainty-based Adaptive Imaging: A noisy measurement is acquired with a scanning
    multiphoton microscope (MPM) and passed into a deep learning model that predicts a denoised image and its associated pixel-wise uncertainty. Subsequently, the top N uncertain pixels are selected for a rescan, obtaining more measurements at only the uncertain regions. As more adaptive measurements are taken, the deep learning model predicts a denoised image with lower uncertainty. Scan duration and power are minimized, limiting sample damage while maintaining high confidence in the model prediction. (b) Rescanning Process: Given a pixel-wise uncertainty prediction, regions with high uncertainty can be selected for rescanning. Only this patch of pixels will be rescanned in the sample, and this patch, superimposed with the original, becomes an additional channel that is fed into the model.

</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/publication_preview/fig_2_architecture.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/publication_preview/fig_4_uncertainty_1_3_5.png
" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

