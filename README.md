# Credit Risk Scorecard - End to End Development

## Overview
An end-to-end credit risk modelling project demonstrating traditional 
scorecard development alongside modern machine learning techniques. 
Built using the German Credit dataset.

## Business Context
Credit scorecards are used by financial institutions to assess the 
probability of default (PD) of loan applicants. This project demonstrates 
the full model development lifecycle from data exploration to model 
validation and explainability.

## Project Structure
- **Data**: German Credit dataset (1,000 records, 21 features, 30% default rate)
- **Target**: Binary classification — Good (0) vs Bad (1) credit risk

## Methodology
### 1. Exploratory Data Analysis
- Target variable distribution analysis
- Default rate assessment

### 2. Feature Selection & WoE Binning
- Information Value (IV) calculation for all features
- Weight of Evidence (WoE) transformation
- 12 predictive variables selected (IV >= 0.02)

### 3. Logistic Regression Scorecard
- WoE-based logistic regression
- Scorecard point scaling
- Score distribution analysis

### 4. XGBoost Model
- Gradient boosting classifier
- Comparison against traditional scorecard
- Overfitting analysis

### 5. Model Validation
- ROC/AUC comparison
- Gini coefficient
- KS Statistic

### 6. Model Explainability
- SHAP values for feature importance
- Feature impact direction analysis
- Regulatory compliance considerations

## Results
| Metric | Logistic Regression | XGBoost |
|--------|-------------------|---------|
| Train AUC | 0.8184 | 0.9890 |
| Test AUC | 0.8239 | 0.7683 |
| Train Gini | 0.6367 | 0.9780 |
| Test Gini | 0.6478 | 0.5365 |
| Overfitting | No | Yes |
| Interpretability | High | Medium |
| Regulatory Friendly | Yes | Partial |

## Key Findings
1. Logistic Regression scorecard achieves stable Gini of ~0.65 with no overfitting
2. XGBoost overfits and requires further tuning before production deployment
3. Top predictive features: Checking Account Status, Credit History, Loan Duration
4. SHAP explainability demonstrates compliance with model governance requirements

## Technologies Used
- Python 3.13
- scorecardpy
- XGBoost
- SHAP
- Scikit-learn
- Pandas, NumPy
- Matplotlib, Seaborn

## How to Run
```bash
# Install dependencies
pip install scorecardpy xgboost shap scikit-learn pandas numpy matplotlib seaborn

# Open notebook
jupyter notebook Credit_Risk_Scorecard_V2.ipynb
```

## Author
NGBGR — Credit Risk & Data Science Professional