# Predicting-County-Health-Outcomes-Using-Machine-Learning-Models

**Author**: Gulnabat Mamedova  
**Course**: Introduction to Statistical Machine Learning  
**Date**: May 2026

---

## Project Overview

This project explores **why some U.S. counties have significantly higher premature death rates** than others by applying machine learning models to predict the **Years of Potential Life Lost (YPLL) Rate** using the 2018 County Health Rankings dataset.

After preprocessing and modeling 2,961 counties with 14 socioeconomic, behavioral, healthcare, and environmental features, **Random Forest** achieved the best performance, explaining **69.1%** of the variation in premature mortality.

**Key Finding**: **% Children in Poverty** is by far the strongest predictor of poor health outcomes.

![Target Variable Distribution](figures/fig1_target_distribution.png)

---

## Goals

1. **Prediction**: Build accurate models to predict the county-level YPLL Rate.
2. **Interpretation**: Identify which factors most strongly drive health disparities.

---

## Dataset

- **Source**: [2018 County Health Rankings](https://www.countyhealthrankings.org/)
- **File**: `2018 County Health Rankings Data`
- **Samples**: 2,961 U.S. counties
- **Target**: `YPLL_Rate` (Years of Potential Life Lost before age 75 per 100,000 population)

### Selected Features (14)
**Socioeconomic**: % Children in Poverty, Income Ratio, Graduation Rate, % Unemployed, % Single-Parent Households  
**Healthcare**: % Uninsured, PCP Rate  
**Health Behaviors**: % Smokers, % Obese, % Physically Inactive, % Excessive Drinking  
**Environment**: Food Environment Index, Average Daily PM2.5, Violent Crime Rate

---

## Repository Files

| File / Folder                    | Description                              |
|----------------------------------|------------------------------------------|
| `2018 County Health Rankings Data` | Original dataset                       |
| `Gulnabat_Mamedova...`           | Main Jupyter Notebook                    |
| `environment`                    | Conda environment file                   |
| `fig1_target_distribution`       | YPLL Rate distribution                   |
| `fig2_correlations`              | Correlation analysis                     |
| `fig3_heatmap`                   | Correlation heatmap                      |
| `fig4_ols_coefficients`          | OLS standardized coefficients            | 
| `fig5_model_comparison`          | Model performance comparison             |
| `fig6_actual_vs_predicted`       | Actual vs Predicted (Random Forest)      |
| `fig7_feature_importance`        | Random Forest Feature Importance         |

---

## Models Used

- Linear Regression (OLS)
- Ridge Regression
- Lasso Regression
- Random Forest Regressor
- Gradient Boosting Regressor

---

## Results

### Model Performance

| Model                    | Test RMSE   | Test R²   | Improvement |
|--------------------------|-------------|-----------|-------------|
| **Random Forest**        | **1348.4**  | **0.691** | **Best**    |
| Gradient Boosting        | 1397.3      | 0.668     | -           |
| Ridge Regression         | 1470.2      | 0.633     | -           |
| Lasso Regression         | 1473.4      | 0.631     | -           |
| OLS Linear Regression    | 1474.5      | 0.631     | Baseline    |

![Model Comparison](figures/fig5_model_comparison.png)

![Feature Importance](figures/fig7_feature_importance.png)

**Top 3 Most Important Features** (Random Forest):
1. **% Children in Poverty** — 44.4%
2. **% Smokers** — 17.7%
3. **% Physically Inactive**

---

## Key Insights

- Child poverty is the dominant driver of premature death rates.
- Smoking has the strongest direct linear effect.
- Non-linear models (Random Forest & Gradient Boosting) significantly outperform linear models.
- Lasso automatically removed `Graduation Rate` and `PCP Rate` due to redundancy.

---

## Setup Instructions

### Using Conda (Recommended)

```bash
conda env create -f environment.yml
conda activate health_ml
jupyter notebook
