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

<h2>Model Architecture and Setup</h2>
<p>For this project, YOLOv8 was chosen for its high efficiency and accuracy in object detection, especially in real-time applications. The following key steps and modifications were made to tailor the model for facemask detection:</p>
<h4><b>Pre-trained Backbone</b></h4>
<p>Leveraging YOLOv8’s pre-trained weights on the COCO dataset provided an excellent foundation, as the network already had baseline knowledge of human facial features and common object boundaries. This initialization reduced the need for extensive training from scratch, allowing the model to converge more quickly while focusing on facemask-specific features.</p>
<h4><b>Fine-tuning</b></h4>
<p>The original YOLOv8 model, built for multi-class detection, was adapted using a customized YAML configuration file that defined three specific classes: "mask worn," "mask not worn," and "mask worn incorrectly." The Ultralytics package was used to implement YOLOv8, providing seamless integration with Weights & Biases (WandB) for real-time metric tracking. Leveraging WandB allowed for detailed logging of key metrics, such as precision, recall, and IoU, streamlining model refinement and performance evaluation.</p>
<h4><b>Data Splitting and Augmentation</b></h4>
<p>Face Mask Detection dataset was used for training and validation. The dataset comprised of 853 images belonging to 3 classes of individuals with varying face orientations, mask types, and in diverse settings, with an 80-20 train-validation split. </p>

<h2>Training and Optimization Process</h2>
<p>Initial training runs highlighted the need for further optimization to stabilize the learning curve and improve accuracy.</p>
<h4>Learning Rate Fine-Tuning</h4>
<p>Early observations indicated that a high learning rate caused fluctuating accuracy and loss values. By incrementally reducing the learning rate using a scheduler, the model achieved smoother convergence, allowing for stable accuracy improvements across epochs.</p>
<h4>Loss function</h4>
<p>To handle the object detection and localization task, YOLOv8’s default loss functions for bounding box regression, objectness, and classification were employed. This included CIoU (Complete Intersection over Union) loss for precise bounding box localization, objectness loss for identifying facemask presence, and cross-entropy loss for multi-class classification among the three classes: "mask worn," "mask not worn," and "mask worn incorrectly."</p>

<!-- The project utilized the YOLOv8 model. This pre-trained model was fine-tuned for our specific application using the FaceMask Detection dataset, which comprises 853 images annotated with bounding boxes, representing three classes: 'No Mask,' 'Mask On,' and 'Mask Incorrectly Worn.'

<h2>Dataset Preparation and Split</h2>

The dataset was meticulously prepared with images labeled according to the PASCAL VOC format, ensuring precise localization of masks on individuals' faces. Adhering to a standard training protocol, the data was split into 80% for training and 20% for validation, optimizing for a balanced exposure to various real-world scenarios during model training.

<h2>Fine-tuning YOLOv8</h2>

Fine-tuning was executed through the Ultralytics framework by modifying a YAML configuration file specific to our dataset. This approach allowed the pre-trained YOLOv8 model to adapt effectively to the nuances of mask detection, enhancing its ability to recognize and classify different mask-wearing conditions accurately.

<h2>Results and Performance Evaluation</h2>

The model's performance was rigorously evaluated through several metrics, crucial for assessing its real-world applicability:

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

<h2>Qualitative Analysis</h2>

Despite the inherent challenges of varying mask types, wearing styles, and lighting conditions, the model demonstrated a robust capability to discern and accurately classify the mask status on individuals

<b>Kaggle notebook:</b> <a href="https://www.kaggle.com/mithildamani/face-mask-detection">here</a>. --> -->