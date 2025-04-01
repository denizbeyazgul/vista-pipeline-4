# VISTA Pipeline 4 - Visual Intelligent System for Threat Analysis

## Overview

**VISTA Pipeline 4** is a machine learning pipeline designed for threat detection and analysis in critical infrastructure systems. This pipeline uses sensor-level data from a water distribution testbed to detect anomalies and explain model decisions with interpretable AI.

> 📌 This pipeline is part of the **VISTA (Visual Intelligent System for Threat Analysis)** project.

## Dataset

The dataset used in this pipeline is:

- **WADI (Water Distribution)**  
  Developed by the **iTrust Centre for Research in Cyber Security** at the **Singapore University of Technology and Design (SUTD)**.  
  It contains sensor data from a real-world water distribution testbed, consisting of **123 different sensor readings**.

## Preprocessing

A key part of this pipeline is robust feature selection and dimensionality reduction. The following steps were applied:

- **Correlation Analysis (Independent Variables):**  
  Examined inter-feature correlations to identify and remove redundant features with high mutual similarity.
  
- **Correlation with Target Variable:**  
  Assessed each feature's predictive relationship with the dependent variable (attack/no attack) and eliminated features with negligible impact.

This preprocessing helped reduce noise and improve model performance and interpretability.

## Model

A **Random Forest Classifier** was trained on the preprocessed dataset.

- Achieved **high accuracy** on the test set
- Chosen for its:
  - Strong performance with high-dimensional sensor data
  - Built-in feature importance estimates
  - Resistance to overfitting

## Model Explainability

To enhance transparency and trust in the model's predictions, both **global and local explainability** techniques were applied using **SHAP (SHapley Additive exPlanations)**:

- **Global SHAP:**  
  Highlights which features are generally most influential in predicting threats.

- **Local SHAP:**  
  Visualizes the contribution of each feature to individual predictions, enabling case-by-case threat investigation.
