# EMG-Based Classification of Healthy and Myopathic Muscle

This repository contains the code and datasets used in our research project: **Classifying Healthy and Unhealthy Muscle Based on Electromyography (EMG)**. The goal is to automate muscle condition assessment using EMG signal analysis combined with traditional feature engineering and machine learning models.

## Project Overview

Electromyography (EMG) is widely used in clinical diagnostics to evaluate muscle health. This project presents a two-stage pipeline:
1. Manual analysis of time- and frequency-domain features to explore trends.
2. Supervised machine learning models for classification of muscle health as **Healthy (H)** or **Myopathic (M)**.


##  Datasets Used

We used two publicly available EMG datasets:

### Dataset 1
- **Subjects**: 12 (6 healthy, 6 myopathic)
- **Movements**: 15 isometric per subject
- **Sampling Rate**: 23,437.5 Hz
- **Duration**: ~11.5 seconds
- **Source**: (Include citation or link if public)

### Dataset 2
- **Subjects**: 100 (50 healthy, 50 myopathic)
- **Movements**: 1 isometric per subject
- **Sampling Rate**: 4096 Hz
- **Duration**: ~5 seconds
- **Source**: (Include citation or link if public)

All signals were pre-segmented into 200 ms windows before feature extraction.

---

##  Methods

###  Preprocessing
- Bandpass filtering (20–450 Hz)
- Normalization
- Segmentation into 200 ms windows

###  Manual Feature Analysis
- **Time-Domain**: MAV, RMS, VAR, SSI, WL, Kurtosis, Skewness, ZC, etc.
- **Frequency-Domain**: FFT, PSD, MNF, MDF
- Plotted and analyzed class trends (Healthy vs. Myopathic)

###  Models
- **Random Forest** (Best performer – accuracy, interpretability)
- **XGBoost** (Boosted tree model with moderate performance)
- **Keras MLP** (Underperformed due to small dataset)
- **CNN on Scalograms** (Deep learning on CWT-transformed images)

## Results

Random Forest Accuracy: ~90% (on combined feature set)
CNN Accuracy: ~92% (on scalogram images)
Manual analysis showed partial feature separation but not reliable for rule-based classification.
