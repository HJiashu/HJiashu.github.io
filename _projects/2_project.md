---
layout: page
title: ZEST
description: ZEro-shot Sparse fine-Tuning
img: assets/img/publication_preview/ZEST_flow.png
importance: 2
category: work
---
Recent studies have pointed out that fine-tuning a subset of layers from the model can match or even outperform the performance of full fine-tuning, known as surgical fine-tuning. This method effectively helps reduce the risks of overfitting and accelerates the fine-tuning process. However, swiftly and accurately identifying the "right" layers is not straightforward. Existing approaches naively train each layer until convergence and find the best candidates, which is not scalable, especially given the rapid growth in model sizes. In this paper, we propose ZEST: Zeroshot Sparse fine-Tuning. We first study and compare the zero-shot metrics acquired from a single forward and backward pass. We observe that the metrics are inconsistent for different model and dataset combinations, thus we train a universal ZEST predictor to generalize this method. We use the zero-shot ZEST predictor to rank layers by the estimated importance and fine-tune only the important parameters. By doing so, we can decrease the number of trainable parameters by up to 90%, while still being able to perform on par with full fine-tuning in terms of model performance. We thoroughly evaluate the effectiveness of ZEST on various tasks and modalities. We train a universal predictor for BERT and LLAMA. And also validate the performance of the method on ResNet50, MobilenetV2, and EfficientNet on 8 different datasets. Notably, our results demonstrate that fine-tuning just twenty-five layers can closely match or even outperform the performance achieved through full fine-tuning on LLaMA-7B

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/publication_preview/ZEST_flow.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Fine-tuning only a mere 10% of parameters can achieve full fine-tuning performance and even outperform full fine-tuning

</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/publication_preview/zestflow-crop.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The overview of our proposed ZEST. Left: We first collect zero-shot forward, backward, and static
metrics from the model. Then, we iterate each layer and record the one-layer fine-tuning accuracy as the ground
truth score. Right: During method training, each iteration, we sample two layers and feed the pre-collected
zero-shot metrics into the predictor. After finishing training, when a new dataset comes in, ZEST only requires
one single minibatch and then can accurately estimate the layers’ importance based on their score


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/publication_preview/results.jpg
" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

ZEST on Large Language Models, as we can see fine-tuning only ZEST selected parameters can outperform full fine-tuning by a small margin

