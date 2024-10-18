---
layout: page
title: Facemask detection
description: Fine-tuned YOLOv8 model for face-mask detection and localization
img: assets/img/dataset-cover.jpg
importance: 1
category: work
related_publications: false
---

Masks play a crucial role in protecting the health of individuals against respiratory diseases, as is one of the few precautions available for COVID-19 in the absence of immunization. With this model, it is possible to detect people wearing masks, not wearing them, or wearing masks improperly.

<b>Kaggle notebook:</b> <a href="https://www.kaggle.com/mithildamani/face-mask-detection">here</a>.

<div class="row">
        <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Face-mask-labels.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
            <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Face-mask-preds.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
The left image displays the ground truth labels for a set of validation images, while the right image shows the model’s predictions with corresponding probabilities. 
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Precision-Recall.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
The graph illustrates the trade-offs between precision (accuracy of positive predictions) and recall (completeness of positive predictions) for each class, highlighting the model’s efficacy in distinguishing among different mask-wearing conditions.
</div>

<div class="row">
        <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/F1-Confidence.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
This curve demonstrates how the F1 score, a balanced measure of precision and recall, varies with different confidence thresholds for the model's predictions on three classes: 'No Mask,' 'Mask On,' and 'Mask Incorrectly Worn'.
</div>
