This project builds an image classification model from scratch to identify diseases in soursop (Annona muricata Linn) leaves using the SoursopBD medicinal plant dataset. The dataset contains 3,838 leaf images collected from real agricultural environments in Kushtia and Dhaka, Bangladesh, categorized into six classes.

# Dataset

Source: https://data.mendeley.com/datasets/hjrhrt5hs8/2

Number of images: 3838

Number of classes: 6

Image Size: 1024 × 1024 pixels

Data Format: .JPG

Name of the classes: Cutting Caterpillar, Cutting Weevil, Die Back, Healthy, White Fly, and Yellow

# Approach

1. Data Preprocessing

Images loaded from structured folders using a custom PyTorch Dataset class

Labels generated from folder names

Dataset split into:
70% Training
15% Validation
15% Testing

Stratified splitting used to preserve class distribution

2. Image Processing & Augmentation

All images resized to 224×224 for computational efficiency.

Training augmentations:

Random horizontal flip

Random rotation

Color jitter (brightness & contrast adjustment)

Validation/Test:

Only resizing and normalization (no augmentation)

# Model Architecture

A Convolutional Neural Network (CNN) built from scratch:

4 convolutional blocks:
Conv2D + BatchNorm + ReLU + MaxPooling

Adaptive Average Pooling

Fully connected classifier:

Linear → ReLU → Dropout → Linear

No pretrained models were used, ensuring training from scratch as per constraints.

# Training Strategy

Loss Function: CrossEntropyLoss

Optimizer: Adam

Learning Rate: 1e-3

Weight Decay (L2 Regularization): 1e-4

Learning Rate Scheduler: ReduceLROnPlateau

Early Stopping: based on validation loss

Batch Size: 32

# Evaluation Metrics

Accuracy

Loss curves (train vs validation)

Classification report (precision, recall, F1-score)

Confusion matrix for class-wise performance analysis


Random horizontal flip
Random rotation
Color jitter (brightness & contrast adjustment)
