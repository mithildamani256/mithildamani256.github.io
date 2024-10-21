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

<h2>The Challenge of Synthetic Image Detection:</h2>

With the Artifact-CycleGAN dataset comprising 15,000 images, split into 80% for training and 20% for validation, the goal was to fine-tune a powerful pre-trained network to classify images as either real or synthetically generated. This binary classification task posed unique challenges, primarily due to the sophisticated quality of AI-generated images which often makes visual differentiation difficult for humans.

<h2>Model Architecture and Training:</h2>

Leveraging the robust architecture of ResNet-50, I adapted this pre-trained network to suit our binary classification needs. By altering the last layer to include a single output neuron with a sigmoid activation function, the model could output a probability score indicating the likelihood of an image being real or AI-generated.

The loss calculation was handled by BCEWithLogitsLoss, which conveniently integrates a sigmoid layer with the binary cross-entropy loss.

<h2>Hyperparameter Tuning and Results:</h2>

Initial training sessions revealed volatile fluctuations in the loss and accuracy graphs, suggesting that the model's learning rate might be too high. Adjusting this rate proved crucial, as a lower learning rate helped stabilize the training process, smoothing out the graphs and enhancing model performance.

<h2>Results Visualization and Analysis:</h2>

Below are the key graphical representations of our project's outcomes:

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

<h2>Qualitative Insights:</h2>

Despite the inherent challenge of visually distinguishing between the dataset's real and AI-generated images, our model demonstrated a remarkable ability to identify underlying patterns that differentiate these categories.

<b>Kaggle notebook:</b> <a href="https://www.kaggle.com/code/mithildamani/synthcheck/">here</a>.