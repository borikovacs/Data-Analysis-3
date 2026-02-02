# Data Analysis 3 - Assignment 1
## Predicting Airbnb Prices in Madrid

**Author:** Borbála Kovács  
**Date:** February 2026

---

## Project Overview

This project develops a pricing model for Airbnb listings in Madrid, Spain. I build and compare 5 predictive models (OLS, LASSO, Random Forest, GBM, HistGBM) using Q1 2025 data, then validate on Q2 2025 Madrid data and Q1 2025 Valencia data.

**Business Case:** Operating a chain of Airbnbs requires accurate pricing. This analysis identifies the best predictive model and key price drivers.

---

## Repository Structure

```
assignment1/
├── code/
│   ├── main_house_price_prediction.ipynb       # Main prediction notebook (run this)
│   ├── house_price_prediction_data_prep.ipynb # Data cleaning (already executed)
│   └── py_helper_functions.py # Supporting package for code
├── data/
│   ├── raw/                          # Original data from Inside Airbnb
│   │   ├── listings_madrid_25q1.csv
│   │   ├── listings_madrid_25q2.csv
│   │   └── listings_valencia_25q1.csv
│   └── clean/                        # Processed data
│       ├── airbnb_madrid_25q1_clean.csv
│       ├── airbnb_madrid_25q2_clean.csv
│       └── airbnb_valencia_25q1_clean.csv
├── output/                           # Figures and tables
│   ├── model_comparison_all.csv
│   ├── ols_model_comparison.png
│   ├── ...
│   └── lasso_lambda_selection.png
└── README.md
```

---

## Data Source

Data obtained from [Inside Airbnb](http://insideairbnb.com/get-the-data):
- **Training:** Madrid, Q1 2025 (~19,000 listings after cleaning)
- **Temporal validation:** Madrid, Q2 2025
- **External validation:** Valencia, Q1 2025

---

## How to Reproduce

### 1. Environment Setup

```bash
# Create conda environment
conda create -n daenv python=3.12
conda activate daenv

# Install required packages
pip install pandas numpy scikit-learn matplotlib seaborn patsy statsmodels
```

### 2. Run the Analysis

Open and run `code/main_house_price_prediction.ipynb` - this notebook:
- Loads the pre-cleaned data
- Builds all 5 models with cross-validation
- Compares model performance
- Validates on external datasets
- **Approximate run time**: 10-12 mins 

The data preparation notebook (`house_price_prediction_data_prep.ipynb`) is executed through the main notebook. You do not need to run it separately.

---

## Models

| Model | Description |
|-------|-------------|
| OLS (M1-M7) | Linear regression with increasing complexity |
| LASSO | L1-regularized regression for variable selection |
| Random Forest | Ensemble of decision trees with bagging |
| GBM | Gradient Boosting Machine |
| HistGBM | Histogram-based Gradient Boosting (LightGBM-inspired) |

---

## Key Features

**Property characteristics:**
- Accommodates, bedrooms, beds, bathrooms
- Property type (Apartment/House)
- Room type (Entire/Private/Shared)

**Quality signals:**
- Review scores, number of reviews
- Superhost status
- Days since first review

**Amenities:** 31 extracted features (WiFi, AC, kitchen, etc.)

**Interactions:** Room type × Property type, Accommodates × Room type

---

## Results Summary

See `output/model_comparison_all.csv` for full results. Intermediate results and descriptive statistics can also be found in the output folder. 

The perminilary descrpitive analysis has been done on the main dataset, the code for that can be found in the `code/backup` folder. The output from the preliminary analysis can also be found in the output folder. 

---

## AI Usage Disclosure

AI (Claude) was used for:
- Code generation and debugging
- Code refactoring
- Documentation formatting

All outputs were verified and validated by the author.

---

## References

- Békés, G. & Kézdi, G. (2021). *Data Analysis for Business, Economics, and Policy*. Cambridge University Press.
- Inside Airbnb: http://insideairbnb.com
