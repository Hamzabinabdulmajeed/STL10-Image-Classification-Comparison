# STL-10: Custom CNN vs. DINOv2 Foundation Model

This project explores the performance gap between training a **Convolutional Neural Network (CNN) from scratch** and using a **Self-Supervised Foundation Model (DINOv2)** for image classification on a small, complex subset of the STL-10 dataset.

## Overview

When data is scarce, "Foundation Models" provide a significant advantage. This experiment uses a tiny subset of STL-10 (246 images across 26 classes) to prove that pre-trained features outperform custom architectures in few-shot learning scenarios.

## Key Results (20 Epochs)

| Metric | CNN (4-Blocks) | DINOv2 + MLP |
| --- | --- | --- |
| **Train Accuracy** | 78.21% | 99.97% |
| **Val Accuracy** | 14.80% | 54.60% |

## Models Used

1. **Custom CNN:** A 4-block architecture (Conv2D -> BatchNorm -> ReLU -> MaxPool) trained from scratch.
2. **DINOv2 (ViT-S/14):** A frozen Vision Transformer backbone from Meta AI, with a custom MLP head trained for classification.

## Exploratory Data Analysis (EDA)

The dataset consists of 26 classes with roughly 9 images per class.

* **Classes include:** *mustelinae, procyonid, airplane, feline, ruminant,* etc.
* **Resolution:** Images are  (resized to  for DINOv2 compatibility).

## How to Run

1. Clone the repo:
```bash
git clone https://github.com/Hamzabinabdulmajeed/stl10-foundation-vs-cnn.git

```


2. Install dependencies:
```bash
pip install -r requirements.txt

```


3. Run the notebook or script.

## Conclusion

The experiment highlights the **overfitting** issues of training from scratch with small dataset sizes (). The CNN memorized the training set (63% gap), while DINOv2 utilized its prior knowledge of 142M images to achieve a validation accuracy **4x higher** than the CNN.

## Kaggle Notebook Link 
https://www.kaggle.com/code/hamzabinbutt/stl-10-cnn-mlp-dinov2/notebook
---
