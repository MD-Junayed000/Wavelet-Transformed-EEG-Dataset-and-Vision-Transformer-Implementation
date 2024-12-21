# Wavelet-Transformed-EEG-Dataset-and-Vision-Transformer-Implementation

**Overview**

This repository explores the use of EEG signals for classifying individuals into alcoholic or control groups. The project involves generating wavelet-transformed scalograms from EEG data and training a Vision Transformer (ViT) model to classify these scalograms with high accuracy.


**Workflow**
The project can be divided into the following stages:


**1. Data Acquisition**

>>Source:

The EEG signals were obtained from the UCI EEG Database https://archive.ics.uci.edu/dataset/121/eeg+database.

>>Data: 64-channel EEG signals sampled at 256 Hz, collected over 1-second intervals.

>>Objective: Examine EEG correlates of genetic predisposition to alcoholism.

**2. Preprocessing**

**Wavelet Transform**

>>**Continuous Wavelet Transform (CWT)** was applied to transform 1D EEG signals into 2D heatmaps (scalograms).

>>Tools and Parameters:

Wavelet: Morlet
Scales: 1 to 255
Sampling Interval: 0.5
Each heatmap represents time-frequency characteristics of a specific EEG channel.

**Dataset Preparation**

>>The processed dataset includes 924 scalograms:

468 for the Alcoholic group.
456 for the Control group.

>>Image Format: JPEG, resized to 200x200 pixels.

**Folder Structure:**

Wavelet_EEG_Dataset/
├── Alcoholic/
│   ├── subject1_channel1.jpg
│   ├── subject1_channel2.jpg
│   └── ...
├── Control/
│   ├── subject2_channel1.jpg
│   ├── subject2_channel2.jpg
│   └── ...

**3. Model Implementation**

**Vision Transformer (ViT)**

A Vision Transformer was implemented for binary classification of scalograms.

**Key Features:**

Divides input images into** 8x8 patches**.
Embeds patches and applies self-attention mechanisms for global context.
Uses **ReLU activation, Adam optimizer,** and dropout regularization.

**Model Architecture**

>>Patch Size: 8x8

>>Embedding Dimension: 64

>>Attention Heads: 3

>>Transformer Layers: 1

>>MLP Units: [8192, 4096]

>>Dropout: 0.1

>>Optimizer: Adam, learning rate = 0.001

**Training**

Dataset: Split into training and validation sets.
Batch Size: 64
Epochs: 16
Augmentations: Applied to improve generalization.

**4. Results**

Performance Metrics
Accuracy: 94.87%
Precision: 94.76%
Recall: 95.10%
F1-Score: 94.93%

**Visualizations**

**Training and Validation Curves:** Loss and accuracy plotted over epochs.

**Confusion Matrix:** Highlights model performance on both classes.

**5. Repository Structure**


Wavelet_EEG_ViT/
├── Wavelet (1).ipynb                  # Notebook for Wavelet Transform
├── ViT_EEG_Alcoholism_Detection.ipynb # Notebook for ViT Implementation
├── Wavelet_EEG_Dataset/               # Processed dataset
│   ├── Alcoholic/
│   └── Control/
├── README.md                          # Project Documentation
├── requirements.txt                   # Python dependencies
└── LICENSE                            # License for the repository
