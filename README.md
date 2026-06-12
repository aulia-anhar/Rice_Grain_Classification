# Deep Learning-Based Rice Grain Classification with Class Imbalance Handling Using Weighted Sampling and Data Augmentation

## Overview

This repository contains the implementation of a rice grain quality classification system based on Deep Learning using the GrainSet dataset. The study focuses on handling class imbalance problems through weighted sampling, data augmentation, and hyperparameter optimization.

Three deep learning architectures were evaluated:

* MobileNetV3
* ResNet50
* ViT-Small (Vision Transformer)

The proposed approach was compared with Focal Loss-Based and Class-Balanced Loss-Based methods to analyze their effectiveness in fine-grained rice grain classification.

---

## Dataset

The experiments use the GrainSet dataset, an annotated grain kernel image database designed for visual quality inspection.

### Rice Quality Classes

| Class | Description      |
| ----- | ---------------- |
| 0_NOR | Normal           |
| 1_F&S | Foreign & Seed   |
| 2_SD  | Slightly Damaged |
| 3_MY  | Chalky / Milky   |
| 4_AP  | Abnormal / Paddy |
| 5_BN  | Broken / Neck    |
| 6_UN  | Unmilled / Husks |
| 7_IM  | Immature / Green |

### Dataset Statistics

* Total Images: 30,962
* Training Images: 27,862
* Testing Images: 3,100
* Number of Classes: 8

---

## Research Objective

The main objective of this study is to investigate the effectiveness of different class imbalance handling strategies for fine-grained rice grain quality classification.

---

## Experimental Scenarios

Six experimental scenarios were evaluated:

### 1. Baseline

Training using the original imbalanced dataset without any class imbalance handling strategy.

### 2. Weighted Sampling

Applying Weighted Random Sampling to improve minority class representation during training.

### 3. Weighted Sampling + Augmentation

Combining weighted sampling with data augmentation techniques.

### 4. Proposed Method

Combining:

* Weighted Sampling
* Data Augmentation
* Hyperparameter Optimization

### 5. Focal Loss-Based

Using Focal Loss as an alternative imbalance handling strategy.

### 6. Class-Balanced Loss-Based

Using Class-Balanced Loss based on the effective number of samples.

---

## Data Augmentation

The following augmentation techniques were applied:

| Technique       | Parameter |
| --------------- | --------- |
| Horizontal Flip | p = 0.5   |
| Vertical Flip   | p = 0.5   |
| Rotation        | ±15°      |
| Brightness      | ±20%      |
| Contrast        | ±20%      |

---

## Model Configuration

### MobileNetV3

* Optimizer: AdamW
* Learning Rate: 1e-3
* Weight Decay: 0.01

### ResNet50

* Optimizer: AdamW
* Learning Rate: 5e-4
* Weight Decay: 0.02

### ViT-Small

* Optimizer: AdamW
* Learning Rate: 1e-4
* Weight Decay: 0.05

Common Settings:

* Epochs: 35
* Batch Size: 64
* Label Smoothing: 0.1
* Scheduler: ReduceLROnPlateau
* Pretrained Weights: ImageNet

---

## Evaluation Metrics

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* Macro F1-Score
* Weighted F1-Score
* Confusion Matrix
* Grad-CAM Visualization

---

## Results

### Baseline

| Model       | Accuracy (%) | Macro F1 |
| ----------- | ------------ | -------- |
| MobileNetV3 | 98.10        | 0.9658   |
| ResNet50    | 97.42        | 0.9580   |
| ViT-Small   | 98.71        | 0.9765   |

### Proposed Method

| Model       | Accuracy (%) | Macro F1 |
| ----------- | ------------ | -------- |
| MobileNetV3 | 98.58        | 0.9772   |
| ResNet50    | 98.87        | 0.9799   |
| ViT-Small   | 97.94        | 0.9683   |

### Best Model

**ResNet50 + Proposed Method**

* Accuracy: 98.87%
* Macro F1-Score: 0.9799
* Weighted F1-Score: 0.9888

---

## Repository Structure

```text
.
├── dataset/
├── notebooks/
├── models/
├── results/
├── figures/
├── README.md
└── requirements.txt
```

---

## Key Findings

* Class imbalance handling improves minority class recognition.
* The proposed method achieved the most consistent performance.
* ResNet50 outperformed MobileNetV3 and ViT-Small.
* CNN-based architectures were more stable than transformer-based models for texture-oriented rice grain datasets with limited training data.

---

## Citation

If you use this work, please cite:

Muhammad Aulia Anhar, Nova Rijati. *Deep Learning-Based Rice Grain Classification with Class Imbalance Handling Using Weighted Sampling and Data Augmentation*.

---

## Author

Muhammad Aulia Anhar
Informatics Engineering
Universitas Dian Nuswantoro
