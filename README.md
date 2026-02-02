# Fuel Blend Property Prediction — Shell.ai Hackathon 2025

## Overview

This project was developed for the **Shell.ai Hackathon for Sustainable and Affordable Energy 2025**. The objective was to build machine learning models to predict final fuel blend properties using component fractions and component-level property data.

We designed a feature-rich ML pipeline with per-target feature selection and adaptive model assignment. Each blend property is modeled separately using the best-performing regressor selected through validation.

**Final Hackathon Score: 90.183**

---

## Problem Statement

Given:

- Fractional composition of multiple fuel components
- Property values of each component

Predict:

- Final blend properties across 10 target variables.

This is a structured multi-target regression task aimed at enabling AI-driven sustainable fuel formulation.

---

## Solution Approach

Instead of using a single model for all targets, we built a **per-target adaptive modeling pipeline**:

- Advanced engineered features
- Recursive Feature Elimination (RFE) per target
- Model selection per property
- Cross-validated evaluation
- Ensemble models where beneficial

Each BlendProperty is trained independently using its best-performing model.

---

## Feature Engineering

We generated extensive engineered features, including:

- Fraction × property interaction features
- Weighted means and weighted variances
- Statistical aggregates across components
- Distribution metrics (skewness, kurtosis)
- PCA components from property space
- Derived blend-level statistical features

Feature selection was then applied using **RFE to select the top 20 features per target**.

---

## Modeling Strategy

For each target property:

- RFE selects best engineered features
- Multiple regressors are evaluated
- Best model is assigned per target

Models used across targets:

- Ridge Regression
- RandomForestRegressor
- HuberRegressor
- Stacking Ensemble
- LightGBM Regressor

This allows each property to use the model that fits it best rather than forcing one global model.

---

## Validation Method

- K-Fold Cross Validation
- Out-of-fold evaluation
- Per-target MAPE reporting
- Model assignment based on validation performance

**Metric:** Mean Absolute Percentage Error (MAPE)

---



