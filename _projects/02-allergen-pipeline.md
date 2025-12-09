---
layout: page
title: Allergen Detection ML Pipeline
description: Machine learning pipeline using Random Forest and Neural Networks to predict IgE levels and detect allergen sensitization from NHANES and ImmPort datasets
img:
importance: 2
category: featured
github: https://github.com/VictorGChen/Allergen-Detection-Pipeline
---

## Overview

A comprehensive machine learning pipeline for allergen detection and IgE level prediction, integrating multi-source clinical datasets (NHANES and ImmPort) with advanced feature engineering and model interpretability analysis.

## Key Features

### Data Engineering
- **Multi-Source Integration**: Combines NHANES (National Health and Nutrition Examination Survey) and ImmPort (Immunology Database and Analysis Portal) datasets
- **Feature Engineering**: Generates 100+ features including sensitization patterns, demographic factors, and seasonal indicators
- **Robust Data Cleaning**: Comprehensive workflows for handling missing data and normalization

### Machine Learning Models
- **Random Forest Regression**: Primary model for IgE level prediction
- **Gradient Boosting**: Enhanced accuracy for complex patterns
- **Neural Networks**: Deep learning approach for non-linear relationships
- **Logistic Regression**: Baseline classification model

### Model Interpretability
- **SHAP Analysis**: SHapley Additive exPlanations for understanding feature importance
- **Feature Impact Visualization**: Clear insights into which factors drive predictions
- **Model Comparison**: Systematic evaluation across multiple architectures

## Technical Capabilities

### Analysis Tasks
- **Classification**: Poly-sensitization detection, IgE categorization
- **Regression**: Serum IgE level prediction
- **Bayesian Modeling**: Probabilistic approach for allergen gene/protein identification

### Production Features
- Robust error handling and logging systems
- Flexible configuration management
- Synthetic data generation for testing
- Comprehensive documentation

## Performance

- **Memory Usage**: 2-4 GB
- **Execution Time**: 20-45 minutes for full pipeline
- **Efficiency**: Optimized for large-scale clinical datasets

## Technologies Used

- Python
- Scikit-learn (Random Forest, Gradient Boosting)
- PyTorch (Neural Networks)
- Pandas & NumPy (Data manipulation)
- SHAP (Model interpretability)
- Bayesian Statistics

## Impact

Enables researchers to identify allergenic patterns from large clinical datasets, contributing to better understanding of allergic responses and potential diagnostic improvements.

## Links

- [GitHub Repository](https://github.com/VictorGChen/Allergen-Detection-Pipeline)
- MIT Licensed with full documentation
- Open for community contributions
