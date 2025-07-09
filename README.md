
# Classification in Asteroseismology

**Artificial Intelligence - Project**  
**University of Sarajevo, June 2025**

## 📋 Project Description

This project focuses on **classification of red giant stars** in asteroseismology using machine learning techniques. The goal is automatic classification of stars into two evolutionary phases:

- **RGB (Red Giant Branch)** - class 0
- **HeB (Helium Burning)** - class 1

## 🎯 Problem Statement

Asteroseismology studies stars based on their oscillations. From oscillations we can:

- Perform evolutionary classification
- Estimate basic physical properties (density, mass, radius)
- Determine star type

Distinguishing RGB from HeB phases is crucial for:

- Determining stellar ages
- Determining ages of galaxies and the universe
- Studying potential life beyond Earth

## 📊 Dataset

- **Source**: [Kaggle - Classification in Asteroseismology](https://www.kaggle.com/datasets/fernandolima23/classification-in-asteroseismology)
- **Size**: 1001 instances (31.4 KB)
- **Format**: CSV
- **Features**:
  - 3 attributes: `Dnu`, `numax`, `epsilon`
  - 1 target variable: `POP` (0=RGB, 1=HeB)
  - Class distribution: 288 RGB (28.8%) / 713 HeB (71.2%)

### Asteroseismic Parameters

| Parameter | Description | Range |
|-----------|-------------|--------|
| `Dnu` | Large frequency separation | 2-17 µHz |
| `numax` | Frequency of maximum oscillation power | 20-240 µHz |
| `epsilon` | Frequency mode offset | 0-1 |

## 🔬 Methodology

### Algorithms Used

1. **Random Forest** (best performance)
2. **Support Vector Machine (SVM)**
3. **Logistic Regression**
4. **Neural Network**

### Data Preprocessing

- **Train/Test Split**: 80/20 (stratified)
- **Standardization**: Z-score normalization
- **Class Imbalance**: Solved using `class_weight="balanced"`
- **Optimization**: GridSearchCV with 5-fold cross-validation

## 📈 Results

### Model Performance (Test Set)

| Model | Accuracy | F1-Score | ROC-AUC |
|-------|----------|----------|---------|
| **Random Forest** | **96.02%** | **97.26%** | **98.29%** |
| SVM | 96.02% | 97.26% | 96.63% |
| Logistic Regression | 95.52% | 96.91% | 97.12% |
| Neural Network | 95.52% | 96.93% | 98.58% |

### Feature Importance (Random Forest)

- **epsilon**: 35.3% - most important parameter
- **numax**: 32.5%
- **Dnu**: 32.1%


## 🔍 Key Findings

1. **Epsilon parameter** proved to be the dominant discriminator between RGB and HeB stars
2. **Random Forest** achieved best performance due to robustness against outliers
3. **Bimodal distribution** of epsilon parameter clearly separates the two classes
4. Model shows **high confidence** for clear cases (epsilon < 0.3 or > 0.8)
5. **Boundary zone** (epsilon 0.4-0.6) requires additional investigation

## 📚 Literature and References

- [Deep Learning Models for RGB and HEB Classification](https://www.techrxiv.org/users/685428/articles/697223-deep-learning-models-for-accurate-classification-of-rgb-and-heb-stars)
- [J-PLUS photometric survey: classification of stellar objects using machine learning](https://academic.oup.com/mnras/article/469/4/4578/3828087)
- [Automatic classification of stellar spectra using deep learning](https://arxiv.org/pdf/1802.07260)
- [GAIA DR1: Accurate stellar spectral types from BP/RP spectra with deep learning](https://arxiv.org/pdf/1705.06405)
- Kepler Mission Data
- TESS Mission Data

## 👥 Team

**Group Members:**
- Denan Poturak
- Hamza Hrnjić
- Safet Čomor

## 📝 Notes

This project was developed as part of the Artificial Intelligence course at the University of Sarajevo. Results demonstrate that traditional machine learning algorithms can be successfully applied to asteroseismic problems with high accuracy.

The project achieved comparable results to state-of-the-art literature (96-97% F1-score vs 98-99% reported in papers), while using a significantly smaller dataset and simpler approaches than deep learning methods typically employed in the field.

