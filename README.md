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

## Results

--- | Metric                 |     Result |
| ---------------------- | ---------: |
| Test Accuracy          | **96.85%** |
| Weighted F1-score      | **96.85%** |
| Mild Impairment F1     | **0.9646** |
| Moderate Impairment F1 | **0.9604** |
| No Impairment F1       | **0.9737** |


## Per-Class Performance


| Metric                 |     Result |
| ---------------------- | ---------: |
| Test Accuracy          | **96.85%** |
| Weighted F1-score      | **96.85%** |
| Mild Impairment F1     | **0.9646** |
| Moderate Impairment F1 | **0.9604** |
| No Impairment F1       | **0.9737** |

## Visualisations

The project includes visualisations of:

Class distribution
Example MRI images
Training and validation accuracy/loss
Normalised confusion matrix
ROC curves

These visualisations were used to assess class imbalance, training behaviour and model performance.

## Key Findings
The CNN achieved 96.85% test accuracy.
Performance remained high across all three classes.
Moderate Impairment achieved 100% recall.
Classification errors primarily occurred between Mild and No Impairment.
Training and validation curves showed stable convergence.
Early stopping and dropout were used to reduce overfitting.
Class weighting was used to address the imbalance between severity categories.
Limitations

## Several limitations should be considered when interpreting the results:

The dataset is relatively modest compared with large-scale neuroimaging datasets.
The dataset originated from a single source, limiting assessment of generalisation across clinical settings.
The model uses 2D MRI slices rather than full 3D brain volumes.
The dataset contained class imbalance despite the use of class weighting.
The model has not been externally validated on an independent multi-centre dataset.
CNN predictions are not inherently interpretable, which may limit clinical transparency.


## Future Work

Potential improvements include:

External validation using multi-centre MRI datasets.
Data augmentation to increase training variability.
Transfer learning using pre-trained CNN architectures.
Investigation of 3D CNN architectures using volumetric MRI data.
Evaluation on more diverse patient populations.
Integration of explainability methods such as saliency maps.
Comparison with alternative deep learning architectures.
