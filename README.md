# 🧠 Alzheimer’s Disease Detection Using MRI Brain Scans

Alzheimer’s is caused because of dementia. Dementia is
not a single disease but rather covers a wide range of specific
conditions including Alzheimer’s disease. These alterations cause a
deterioration in thinking abilities, also known as cognitive
capacities, that is severe enough to impair day-to-day activities.
There are 3 stages of Alzheimer’s Disease Mild Cognitive
impairment (MCI), Moderate Alzheimer's Disease and Severe
Alzheimer's Disease. The symptoms of Alzheimer’s Disease are
many, but the common and important signs are Memory loss,
challenges solving problems, difficulty completing familiar tasks,
lose track of time. There is no treatment that can slow or stop the
progression of Alzheimer's disease. There are types of drugs that
attempt to treat the cognitive symptoms and slow down the
progression.

## 📌 Project Overview

This project explores an advanced approach to early-stage Alzheimer’s Disease (AD) detection through the analysis of MRI brain scans. Leveraging both classical and modern AI techniques, it involves a comparative study between traditional **Convolutional Neural Networks (CNNs)**, various **Vision Transformers (ViTs)**, and **machine learning classifiers**, aiming to identify the most effective model for classification and diagnosis.
MRI scans were sourced from the **ADNI (Alzheimer's Disease Neuroimaging Initiative)** and **Kaggle** datasets. These scans were processed to detect deterioration in critical brain regions (hippocampus, cortex, corpus callosum), which are indicative of Alzheimer's disease progression. The classification involved categorizing the scans into four stages: **Non-Demented**, **Very Mild Demented**, **Mild Demented**, and **Severe Demented**.

## 🧪 Objectives

- Analyze and classify brain MRI scans to detect Alzheimer’s stages.
- Compare performance between CNN, ViTs (Vanilla ViT, DeepViT, CaiT), and ML models (SVM, Random Forest).
- Identify the most accurate and efficient model for early-stage detection.
- Explore deep learning vs. transformer-based vision models in the medical imaging domain.

## 📊 Data & Preprocessing

- **Datasets Used**:
  - *ADNI Dataset*: High-quality ~6400 MRI scans used for training deep learning and transformer models.
  - *Kaggle Alzheimer’s Dataset*: Contains MRI scans categorized into four AD stages.

- **Preprocessing**:
  - Image normalization and resizing to 128×128 pixels.
  - Image augmentation (flipping, zooming) to enhance data variety.
  - Intensity normalization and pixel scaling to fit neural network input layers.

## 🏗️ Model Architectures

## 📉 Machine Learning Baselines
Before applying deep learning, traditional ML models were tested using features extracted from MRI images via NASNetMobile:
- **SVM**: Accuracy = 48%
- **Random Forest**: Accuracy = 82%

## CNN (Convolutional Neural Network)
- Utilized 2D convolutional and max-pooling layers.
- Achieved **82% accuracy**.
- Best performance among traditional deep learning methods.

## Vision Transformers (ViTs)
Transformers process visual data using attention mechanisms instead of convolution, suitable for capturing global dependencies in images.

### 🔸 Vanilla ViT
- Basic transformer architecture with positional embeddings.
- **Accuracy**: 56.41%

### 🔸 DeepViT
- Enhanced ViT with **Re-attention layers** to avoid similarity collapse in deep layers.
- **Accuracy**: **90.2%** (Highest)

### 🔸 CaiT (Class Attention in Image Transformer)
- Introduces class-attention layers and CLS token to focus on key image regions.
- Two configurations:
  - **CaiT128-8**: 74.52%
  - **CaiT128-16**: 80.27%

## ⚙️ Training Strategy

- **Optimizers**: AdamW, SGD (StepLR scheduler)
- **Epochs** & **Dropout** for regularization
- **Fine-tune**: Updates only the patch embeddings and classifier layers.
- **Checkpoint**: Freezes the transformer for 50 epochs, then unfreezing for low-rate learning..

## 🧩 Conclusion

This project demonstrates that **Vision Transformers**, particularly **DeepViT**, outperform CNNs and classical ML models in MRI-based Alzheimer's disease classification. The **Re-attention mechanism** in DeepViT enhances attention diversity across layers, resulting in more accurate classification of disease stages.

## 🔮 Future Work

- **Hybrid Approach**: Combine CNN and ViT to create a Convolutional Vision Transformer (CVT).
- **Real-World Integration**: Implement in clinical environments.
- **Awareness & Adoption**: Promote understanding and trust in AI-powered medical diagnostics.

## 📌 Citation

If you use this project or refer to it in your work, please cite the original research paper:

Sherwani, P., Nandhakumar, P., Srivastava, P., Jagtap, J., Narvekar, V., & Harikrishnan, R. (2023). *Comparative Analysis of Alzheimer’s Disease Detection via MRI Scans using Convolutional Neural Network and Vision Transformer*. International Conference on Electronics and Communication. IEEE.
https://www.researchgate.net/publication/369769262_Comparative_Analysis_of_Alzheimer's_Disease_Detection_via_MRI_Scans_Using_Convolutional_Neural_Network_and_Vision_Transformer/citations

## 📚 References

- Kaggle Dataset: https://www.kaggle.com/datasets/tourist55/alzheimers-dataset-4-class-of-images  
- ADNI Dataset: https://adni.loni.usc.edu  
- Additional references are cited within the original research paper.
