# Predicting County Health Outcomes Using Machine Learning

**Author**: Gulnabat Mamedova  
**Course**: Introduction to Statistical Machine Learning  
**Date**: May 2026

---

## Project Overview

This project uses machine learning to predict **premature death rates** (Years of Potential Life Lost Rate - YPLL) across **2,961 U.S. counties** using the 2018 County Health Rankings dataset.

The goal was to accurately predict health outcomes and understand which socioeconomic, behavioral, and environmental factors matter most.

**Best Model**: Random Forest (Test RMSE = 1,348.4 | R² = 0.691)

**Key Finding**: **% Children in Poverty** is by far the strongest predictor of poor county health outcomes.

---

## Dataset

- **File**: `2018 County Health Rankings Data`
- **Samples**: 2,961 counties
- **Target Variable**: YPLL Rate (Years of Potential Life Lost before age 75 per 100,000)

---

## Repository Contents

| File                              | Description                                      |
|-----------------------------------|--------------------------------------------------|
| `Main.ipynb`                      | Main Jupyter Notebook (updated name)             |
| `2018 County Health Rankings Data`| Original Excel dataset                           |
| `environment`                     | Conda environment files                          |
| `fig1_target_distribution.png`    | Target variable distribution                     |
| `fig2_correlations.png`           | Feature correlations                             |
| `fig3_heatmap.png`                | Correlation heatmap                              |
| `fig4_ols_coefficients.png`       | OLS regression coefficients                      |
| `fig5_model_comparison.png`       | Model performance comparison                     |
| `fig6_actual_vs_predicted.png`    | Actual vs Predicted plot                         |
| `fig7_feature_importance.png`     | Random Forest feature importance                 |

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

| Model                    | Test RMSE   | Test R²   | vs OLS      |
|--------------------------|-------------|-----------|-------------|
| **Random Forest**        | **1348.4**  | **0.691** | **Best**    |
| Gradient Boosting        | 1397.3      | 0.668     | -           |
| Ridge                    | 1470.2      | 0.633     | -           |
| Lasso                    | 1473.4      | 0.631     | -           |
| OLS Linear Regression    | 1474.5      | 0.631     | Baseline    |

![Model Performance](figures/fig5_model_comparison.png)

![Feature Importance](figures/fig7_feature_importance.png)

**Top Features (Random Forest Importance)**:
1. **% Children in Poverty** — 44.4%
2. **% Smokers** — 17.7%
3. **% Physically Inactive**

---

## Setup Instructions

### Option 1: Conda (Recommended)

```bash
conda env create -f environment.yml
conda activate health_ml
jupyter notebook
