---
layout: page
title: SynthCheck
description: AI model for Synthetic vs. Real Image classification
img: assets/img/dataset-cover.png
importance: 1
category: work
related_publications: true
---

In an era where digital content can be crafted and manipulated with alarming ease, the line between reality and artificiality blurs, presenting not only technological advancements but also ethical dilemmas and potential dangers. Deepfake technology, a profound testament to AI's capabilities, allows for the creation of incredibly realistic images and videos that are nearly indistinguishable from authentic content. This rise in synthetic media poses significant risks, from misinformation to identity theft, making it imperative to develop robust mechanisms for discerning these AI-generated fabrications from genuine images.

<b>Kaggle notebook:</b> <a href="https://www.kaggle.com/code/mithildamani/synthcheck/">here</a>.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/trainval-accuracyloss.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
The left graph displays the training and validation loss per epoch, indicating how the model's error rates decreased over time. The right graph shows the training and validation accuracy per epoch, illustrating improvements in the model's ability to correctly classify images.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/confusion_matrix.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
The plot illustrates the performance of the classifier in distinguishing real images from AI-generated ones. The diagonal cells represent correctly classified images (True Positives and True Negatives), while the off-diagonal cells indicate misclassifications (False Positives and False Negatives).
</div>
