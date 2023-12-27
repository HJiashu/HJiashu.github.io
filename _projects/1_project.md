---
layout: page
title: OTF 
description: On-the-fly Transfer-learning Framework for Isotropic Resolution in Volumetric Imaging
img: assets/img/publication_preview/otf.jpg
importance: 1
category: work
related_publications: einstein1956investigations, einstein1950meaning
---

Every project has a beautiful feature showcase page.
It's easy to include images in a flexible 3-column grid format.
Make your photos 1/3, 2/3, or full width.

To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---


<div class="row justify-content-sm-cente">
    <div class="col-sm-12 mt-3 mt-md-0">
        {% include figure.html path="assets/img/axial_gt_less_frames.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

The overview of our proposed ZEST. Left: We first collect zero-shot forward, backward, and static
metrics from the model. Then, we iterate each layer and record the one-layer fine-tuning accuracy as the ground
truth score. Right: During method training, each iteration, we sample two layers and feed the pre-collected
zero-shot metrics into the predictor. After finishing training, when a new dataset comes in, ZEST only requires
one single minibatch and then can accurately estimate the layers’ importance based on their score

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>
<!-- 

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}
```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
    
        {% include figure.html path="assets/img/axial_gt_less_frames.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/axial_gt_less_frames.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
```
{% endraw %} -->
