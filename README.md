# Intelligent Air Compressor Fault Diagnosis using Multi-Domain Feature Extraction and Machine Learning

> Course Project | EE656: Artificial Intelligence Applications | Indian Institute of Technology Kanpur

---

## Project Overview

This repository presents an implementation of an intelligent condition-based monitoring framework for reciprocating air compressors using acoustic emission signals. The project was developed as part of the **EE656: Artificial Intelligence Applications** course at the **Indian Institute of Technology Kanpur** under the guidance of **Prof. Nischal K. Verma**.

The implementation follows the operational methodology proposed by **Verma et al.**, combining multi-domain signal processing, feature selection, and machine learning to accurately classify multiple compressor fault conditions.

The complete framework extracts complementary features from multiple signal transformation techniques, performs feature selection using the **Minimum Redundancy Maximum Relevance (mRMR)** algorithm, and classifies compressor faults using a **One-Against-One (OAO) Support Vector Machine** with an RBF kernel.

---

## Project Information

| Item | Details |
|------|---------|
| **Course** | EE656 – Artificial Intelligence Applications |
| **Institution** | Indian Institute of Technology Kanpur |
| **Instructor** | Prof. Nischal K. Verma |
| **Project Type** | Course Project |
| **Language** | Python |
| **Development Environment** | Google Colaboratory |

---

## Features

- Multi-domain acoustic signal analysis
- Feature extraction using:
  - Fast Fourier Transform (FFT)
  - Discrete Cosine Transform (DCT)
  - Short-Time Fourier Transform (STFT)
  - Wigner–Ville Distribution (WVD)
  - Wavelet Packet Transform (WPT)
- Construction of a unified **414-dimensional feature vector**
- Feature selection using **Minimum Redundancy Maximum Relevance (mRMR)**
- Hyperparameter optimization using Grid Search
- Fault classification using **One-Against-One Support Vector Machine (OAO SVM)**
- Performance evaluation using **Stratified 5-Fold Cross-Validation**

---

## Methodology

```
Acoustic Signal
        │
        ▼
+--------------------------------------+
| Multi-Domain Feature Extraction      |
| FFT | DCT | STFT | WVD | WPT         |
+--------------------------------------+
        │
        ▼
414-Dimensional Feature Vector
        │
        ▼
Minimum Redundancy Maximum Relevance
            (mRMR)
        │
        ▼
Top 25 Features
        │
        ▼
Grid Search
        │
        ▼
OAO Support Vector Machine (RBF)
        │
        ▼
Fault Classification
```

---

## Experimental Results

| Parameter | Value |
|-----------|------:|
| Number of Classes | 8 |
| Total Samples | 1800 |
| Initial Features | 414 |
| Selected Features | 25 |
| Feature Selection | mRMR |
| Classifier | OAO SVM (RBF Kernel) |
| Validation Strategy | Stratified 5-Fold Cross-Validation |
| Classification Accuracy | **99.56%** |

The implemented framework successfully reproduces the operational diagnosis strategy proposed by Verma *et al.* and achieves an overall classification accuracy of **99.56%**, closely matching the performance reported in the reference study.

---

## Repository Structure

```
air-compressor-fault-diagnosis/
│
├── notebooks/
│   ├── feature_extraction.ipynb
│   └── feature_selection_svm.ipynb
│
├── models/
│   ├── feature_selector.pkl
│   ├── scaler.pkl
│   └── svm_model.pkl
│
├── reports/
│   ├── Project_Report.pdf
│   └── Presentation.pdf
│
├── results/
│   ├── confusion_matrix.png
│   ├── grid_search_heatmap.png
│   └── mrmr_transform_distribution.png
│
├── requirements.txt
│
└── README.md
```

---

## Dataset

The experiments were conducted using a preprocessed acoustic emission dataset provided as part of the EE656 course project.

Dataset characteristics:

- **1800 acoustic recordings**
- **8 operating conditions**
- **225 samples per operating condition**
- **Sampling Frequency:** 50 kHz
- **Preprocessed `.dat` files**

The original dataset is **not included** in this repository due to course distribution restrictions.

---

## Technologies Used

- Python
- NumPy
- SciPy
- Pandas
- Scikit-learn
- PyWavelets
- Matplotlib
- Google Colaboratory

---

## Learning Outcomes

This project provided practical experience in:

- Signal processing for machinery condition monitoring
- Multi-domain feature engineering
- Statistical feature selection using mutual information
- Machine learning for fault diagnosis
- Hyperparameter optimization
- Model evaluation using cross-validation
- Scientific computing with Python

---

## References

1. N. K. Verma and A. K. Darpe, *Intelligent Condition Based Monitoring Using Acoustic Signals for Air Compressors*, IEEE Transactions on Instrumentation and Measurement.

2. H. Peng, F. Long, and C. Ding, *Feature Selection Based on Mutual Information: Criteria of Max-Dependency, Max-Relevance, and Min-Redundancy*, IEEE Transactions on Pattern Analysis and Machine Intelligence.

---

## Acknowledgements

This repository contains the implementation developed as part of the **EE656: Artificial Intelligence Applications** course project at the **Indian Institute of Technology Kanpur** under the guidance of **Prof. Nischal K. Verma**.

The implementation follows the intelligent fault diagnosis methodology proposed by **Verma et al.** for reciprocating air compressors using acoustic emission signals. The objective of this project was to implement the recommended operational framework—including multi-domain feature extraction, mRMR feature selection, and OAO Support Vector Machine classification—and evaluate its performance on the provided acoustic dataset.

This repository is intended solely for educational and academic purposes.
