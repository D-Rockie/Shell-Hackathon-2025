Fuel Blend Property Prediction — Shell.ai Hackathon 2025
Overview

This project was developed as part of the Shell.ai Hackathon for Sustainable and Affordable Energy 2025. The challenge focused on predicting the final properties of sustainable fuel blends based on their component fractions and chemical properties.

The objective was to build high-accuracy machine learning models that can estimate multiple blend properties, helping accelerate sustainable fuel formulation using AI-driven prediction.

Our solution achieved a validation score of 90.183 using an advanced stacking ensemble approach.

Problem Statement

Given:

Fractional composition of multiple fuel components

Property values for each component

Predict:

Final blended fuel properties across multiple target variables.

This is a multi-target regression problem involving structured numerical data and domain-driven feature interactions.

Approach Summary

We built a high-performance regression pipeline combining:

Advanced feature engineering

Statistical aggregation features

Weighted component-property interactions

PCA-based dimensionality reduction

Multi-model stacking ensemble

The system predicts all blend properties using cross-validated ensemble learning.

Feature Engineering

Key engineered features include:

Fraction × property interaction features

Weighted mean and variance of component properties

Statistical aggregations (min, max, mean, std)

Distribution metrics (skewness, kurtosis)

PCA components from property space

Blend-level derived signals

This expanded the feature space significantly and improved predictive signal.

Models Used

We used a stacking-style weighted ensemble of:

LightGBM Regressor — primary high-performance learner

Random Forest Regressor — nonlinear stability model

Ridge Regression — linear regularized baseline

Model weights were computed using inverse validation MAPE scores for each target.

Validation Strategy

5-Fold Cross Validation

Out-of-fold predictions for each base model

Weighted ensemble based on validation performance

Metric: Mean Absolute Percentage Error (MAPE)

Final Performance

Validation Score: 90.183

Ensemble consistently outperformed individual base models across targets.

Tech Stack

Python

Pandas, NumPy

LightGBM

Scikit-learn

PCA

SciPy statistics (skew, kurtosis)
