---
layout: page
title: OTF 
description: On-the-fly Transfer-learning Framework for Isotropic Resolution in Volumetric Imaging
img: assets/img/publication_preview/otf.jpg
importance: 1
category: work
---
One intrinsic yet essential issue that has plagued the field of fluorescence microscopy ever since its creation is the unmatched resolution in the lateral and axial directions namely the resolution anisotropy. This anisotropy severely deteriorates the quality, reconstruction, and analysis of 3D volumetric images. Aimed at solving this problem, we propose the OTF framework to enhance axial resolution. 
In contrast to the existing deep learning approaches that either require matched high-resolution target images, suffer from hallucination, or require huge computational training time, our method can reconstruct original data with high fidelity, while requiring only a single 3D image stack, and can finish the whole process under 5 minutes, achieving real-time reconstruction. Using multiphoton microscopy, confocal microscopy, and light-sheet microscopy, we demonstrate that our framework not only enhances axial resolution but also restores visual details between the imaging planes and removes imaging artifacts.
With our method, we can unveil insights into the frequency, mass, and distribution of nucleoli/nuclei in human endometrium samples, paving the way for accurate 3D cell phenotyping.



<div class="row justify-content-sm-cente">
    <div class="col-sm-12 mt-3 mt-md-0">
        {% include figure.html path="assets/img/publication_preview/otf.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


<div class="caption">
    Generalizability of OTF, we used ZEST to choose important layers to fine-tune for each different modality
</div>
Instead of viewing the 3D stack data as an entirety, we sliced it into 2D image sets containing multiple lateral and axial planes. As the stream of images is collected, we denoise the high-resolution lateral images, use them as the rational gold standard, and computationally modify them to resemble anisotropic axial slices of the same image stack to serve as the semi-synthetic dataset. Then we modify selected parameters from a pre-trained general-purpose deblurring network using the semi-synthetic dataset. In this way, not only is a single raw image stack sufficient for network training but also the whole procedure can take around 5 to 10 minutes.
To overcome the recovery infidelity and the long training time that plagues CARE, we generate semi-synthetic data via denoised lateral images and adopt a variety of different PSF models. These two differences are key to overcoming the hallucination problem that CARE suffers from. 
Denoising lateral images is due to the reason that the convolutional forward process and the additive noise are separate processes. Directly applying a PSF kernel on the noisy data in the lateral plane will also convolve the additive noise, leading to a large discrepancy between the training dataset distribution and the target dataset distribution. Thus, denoising before computationally modifying the data can fundamentally decrease the gap between the semi-synthetic data and the actual real data.
Using a variety of different PSFs for generating the semi-synthetic data is also a step towards alleviating hallucinations. Using a forward model to generate the PSF is possible in theory. However, in real applications, where the PSF often varies due to aberration and depth, using a simple theoretical model might not always prove faithful. Especially for multi-photon microscopy, where the tissues are often imaged at an extensive depth within the sample, where the PSF will be distorted. Towards this end, we propose to utilize a pre-trained neural network on real-life general-purpose deblurring tasks, then modify key parameters within the network to adapt to the microscopy data.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/axial_gt_less_frames.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
Results on human endometrium samples
</div>
