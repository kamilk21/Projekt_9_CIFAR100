# CIFAR-100 Classification and Feature Extraction with PyTorch

This project compares traditional CNN classification with feature-based k-NN and cosine-similarity classification on subsets of the CIFAR-100 dataset.  
It demonstrates how a convolutional network trained on one part of the dataset can serve as a feature extractor for classification tasks.

---

## Project Overview

The goal is to compare two approaches:

1. Stage 1 – Traditional CNN classification
   - A standard convolutional neural network based on ResNet-18 is trained on 50 classes from CIFAR-100.

2. Stage 2 – Feature-based classification (Part A)
   - The trained CNN is used as a feature extractor.
   - For each class, subsets of 1, 5, and 10 training samples are selected.
   - Classification is performed using cosine similarity between test image features and training samples.

3. Stage 3 – Transfer to unseen classes (Part B)
   - The same feature extractor (trained on the first 50 classes) is used to classify images from the remaining 50 classes using the same cosine-based approach.

---

## Results

### Stage 1
After 25 epochs, the CNN achieved 52.94% accuracy on the test split (50 classes).

### Stage 2 
#### Part A – Classes seen during training

| Subset size | Accuracy |
|--------------|-----------|
| 1 sample per class | **24.68%** |
| 5 samples per class | **35.82%** |
| 10 samples per class | **40.68%** |

### Stage 3 
#### Part B – Unseen classes

| Subset size | Accuracy |
|--------------|-----------|
| 1 sample per class | **12.88%** |
| 5 samples per class | **20.12%** |
| 10 samples per class | **21.16%** |
