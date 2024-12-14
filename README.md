---

# Benchmarking Spatial-Aware Classification Models for Urothelial Cancer Subtypes

This project benchmarks spatial-aware classification models for distinguishing muscle-invasive (MIUC) from non-muscle-invasive urothelial cancer (NMIUC) using [Mass Spectrometry Imaging (MSI) data](https://www.ebi.ac.uk/pride/archive/projects/PXD026459). By developing accurate and robust models, we aim to optimize resource allocation, improve patient care, and enhance clinical outcomes for urothelial cancer patients.

## Overview

Mass Spectrometry Imaging (MSI) is a cutting-edge technology that generates spatially resolved mass-to-charge ratio (m/z) data from tissue samples. MSI provides a unique opportunity to identify tumor boundaries, classify cancer subtypes, and uncover disease-specific molecular signatures. This project utilizes MALDI-MSI (Matrix-Assisted Laser Desorption Ionization) to extract and analyze data from bladder tissue samples of 47 patients.

## Dataset

- **Sources**: The dataset includes 49 bladder tissue cores, processed and labeled using the European Galaxy server to ensure transparency and reproducibility.
- **Format**: 
  - *imzML Files*: Metadata (e.g., coordinates, spectra) that map spatial and structural features.
  - *ibd Files*: Binary data storing m/z and intensity measurements.
  - *Annotation Files*: Pathologist-annotated labels, including histology, diagnosis, invasiveness, and positional coordinates.
- **Public Access**: Available in the Proteomics IDEntifications Database under project code PXD026459.

### Challenges:
- Class Imbalance: Non-muscle-invasive samples are underrepresented.
- High Dimensionality: Thousands of ion intensity distributions require robust analysis.

## Methodology

Our analysis pipeline involves:
1. **Data Preprocessing**:
   - Normalization with TIC scaling.
   - Filtering tumor and stromal regions while maintaining spatial integrity.
2. **Exploratory Analysis**:
   - Visualization of tissue histology and mass spectra using tools like ggplot2.
   - Identification of discriminative spectral features.
3. **Classification Models**:
   - **Spatial Shrunken Centroids (SSC)**: Captures spatial context and regional variations.
   - **Random Forest (RF)** and **XGBoost (XGB)**: Robust tree-based ensemble methods.
   - **Partial Least Squares (PLS)**: Detects latent spectral structures.
4. **Addressing Imbalance**:
   - Applied Synthetic Minority Oversampling Technique (SMOTE).

### Performance Metrics:
- Accuracy, sensitivity, specificity, F1 score, and ROC curves.
- Rigorous cross-validation using TMA2 (training, n=788) and TMA1 (testing, n=678).

## Results

- **Random Forest**:
  - Accuracy: 82.7%
  - Sensitivity: 90.4%
  - Specificity: 71.0%
  - Top m/z Features: 1407.00, 1235.00.
- **XGBoost**:
  - Accuracy: 82.4%
  - Sensitivity: 96.3%
  - Specificity: 61.3%
  - Top Feature: m/z 838.
- **SSC**:
  - Specificity: 97.0% (best for detecting non-invasive cases).
  - Sensitivity: 47.2% (requires refinement for invasive cases).
- **PLS**:
  - Balanced Accuracy: 60.3%.

### Insights:
- Random Forest and XGBoost demonstrated the most balanced performance, while SSC excelled in specificity.
- Feature importance analysis highlighted key m/z ranges for classification.

## Discussion

This project illustrates the potential of spatial-aware algorithms in MSI-based cancer subtype classification. While SSC provides high specificity, its sensitivity limitations restrict clinical utility. Tree-based models like Random Forest and XGBoost offer a more balanced trade-off and promise as diagnostic tools. Further optimization, such as feature selection and multi-model integration, is needed to achieve clinically reliable results.




--- 
