# Deep Learning for Dementia Classification Using MRI Images

## Overview

This project investigates the use of a Convolutional Neural Network (CNN) to classify brain MRI images into three dementia severity categories:

- No Impairment
- Mild Impairment
- Moderate Impairment

The project explores how deep learning can be applied to medical image classification while addressing challenges such as class imbalance, overfitting and model generalisation.

The final CNN achieved an overall test accuracy of **96.85%** and a weighted F1-score of **96.85%**, with ROC-AUC values of **≥0.99** across the three classes.

> **Note:** This project is for academic and research purposes. The model has not been clinically validated and should not be used for medical diagnosis.

---

## Project Objectives

The main objectives were to:

1. Develop a CNN for multi-class dementia severity classification from MRI images.
2. Preprocess and standardise MRI images for model training.
3. Address class imbalance using class-weighted loss.
4. Evaluate model performance using multiple classification metrics.
5. Assess model generalisation using an independent test set.
6. Investigate potential limitations and ethical considerations associated with AI-based medical imaging.

---

## Dataset

The dataset contains **5,076 greyscale brain MRI images** classified into three categories:

| Class | Description |
|---|---|
| No Impairment | MRI images classified as showing no cognitive impairment |
| Mild Impairment | MRI images associated with mild cognitive impairment |
| Moderate Impairment | MRI images associated with moderate cognitive impairment |

The images were resized to **224 × 224 pixels** and normalised to a pixel intensity range of **0–1**.

### Class Distribution

The dataset was imbalanced, with Moderate Impairment being the smallest class.

To reduce the effect of this imbalance during training, class weights were applied:

| Class | Weight |
|---|---:|
| Mild Impairment | 0.944 |
| Moderate Impairment | 2.336 |
| No Impairment | 0.661 |

The dataset was divided using a stratified split:

- **70% Training**
- **15% Validation**
- **15% Testing**

A fixed random seed (`42`) was used to support reproducibility.

--- 


