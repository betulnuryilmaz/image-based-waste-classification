# Image-Based Waste Classification for Recycling

This repository contains the implementation of the **Image-Based Waste Classification for Recycling** project, developed as part of the DSAI544 - Computer Vision with Machine Learning course. The project explores the application of computer vision and self-supervised learning techniques to address challenges in automated waste sorting and recycling.

---

## 📂 Project Structure

- **`GarbageClassification.ipynb`**: The primary notebook with all the implementation steps.
- **`requirements.txt`**: List of dependencies required to run the project.
- **`README.md`**: Documentation of the project.


---

## 📋 Project Overview

### **Objective**
To develop a scalable and robust solution for waste sorting automation using computer vision. The solution leverages self-supervised learning techniques to classify waste items into 10 categories, contributing to sustainable recycling efforts.

### **Dataset**
The dataset was sourced from Kaggle(https://www.kaggle.com/datasets/sumn2u/garbage-classification-v2) and includes **19,762 images** distributed across the following categories:
- Metal: 1,020 images
- Glass: 3,061 images
- Biological: 997 images
- Paper: 1,680 images
- Battery: 944 images
- Trash: 947 images
- Cardboard: 1,825 images
- Shoes: 1,977 images
- Clothes: 5,327 images
- Plastic: 1,984 images

The images were preprocessed with data augmentation techniques such as resizing, cropping, flipping, and color jittering to ensure robustness.

---

## 🛠 Methodology

The project is structured into three main phases:
1. **Pre-training**:
   - Used **SimCLR (Simple Contrastive Learning)** for self-supervised learning on an unlabeled dataset.
   - Backbone model: **ResNet-18** with a projection head.
   - Loss function: **Contrastive Loss** with cosine similarity.
   - Optimizer: **Adam** with a learning rate scheduler.

2. **Fine-Tuning**:
   - Adapted the pre-trained model to the labeled dataset.
   - Used a **classification head** to map feature vectors to categories.
   - Loss function: **Cross-Entropy Loss** for supervised learning.

3. **Hyperparameter Tuning**:
   - Random search was applied to optimize hyperparameters (learning rate, weight decay, dropout rate, and batch size).
   - Best configuration: **Learning rate = 0.0001, Weight decay = 1e-5, Dropout = 0.3, Batch size = 64**.

---

## 📊 Results

### **Performance Metrics**
- **Validation Accuracy**: 91.31% (after hyperparameter tuning)
- **Test Accuracy**: 88.25%
- Misclassification analysis identified challenges in differentiating visually similar categories like "Glass" and "Shoes".

### **Visualization**
Graphs for training/validation loss and accuracy are available in the notebook, along with sample predictions for qualitative analysis.

---

## 🚀 Getting Started

### **Prerequisites**
- Python 3.x
- Required libraries listed in `requirements.txt`.

### **Steps to Run**
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/repository-name.git
   cd repository-name
