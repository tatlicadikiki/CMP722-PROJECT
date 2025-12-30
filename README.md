# CMP722-PROJECT

Scene Change Detection with CLIP & Strong AugmentationCourse Project: CMP 722 - Advanced Computer Vision (Hacettepe University)

Author: Bengisu Adsız AbstractThis project implements a robust Scene Change Detection system using OpenAI's CLIP (ViT-B/32) model. The goal is to detect semantic changes between image pairs while ignoring "cosmetic" variations caused by seasonal transitions (Summer vs. Winter), lighting, or camera shifts.To achieve semantic invariance, a Strong Data Augmentation pipeline was developed, forcing the model to learn high-level features rather than trivial pixel matching. The model was trained on the Yosemite Summer-to-Winter dataset and achieved 87.41% Accuracy on the test set.

Key Features

Backbone: Frozen CLIP (ViT-B/32) for zero-shot capable feature extraction.
Classifier: Lightweight MLP (Multi-Layer Perceptron) with Dropout for binary classification.
Strong Augmentation: An aggressive pipeline including:Random Rotation ($\pm 5^\circ$) & Resized Crop.Color Jitter (Brightness, Contrast, Saturation).Gaussian Blur & Random Grayscale.
Robustness: High recall (0.95) on identifying the "Same Scene" despite heavy augmentations.

Dataset

The project utilizes the Yosemite Summer-to-Winter dataset (originally from CycleGAN papers).

Content: Unpaired images of Yosemite National Park in summer and winter.

Structure:

Positive Pairs (Same Scene): Generated via strong augmentation of a single image.
Negative Pairs (Different Scene): Randomly paired Summer and Winter images.
Split: 900 Pairs (70% Train, 15% Val, 15% Test).
