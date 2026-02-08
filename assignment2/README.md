# Data Analysis 3 - Assignment 2
## Finding Fast Growing Firms

**Authors:** Borbala Kovacs and Muheng Li
**Date:** February 2026

---

## Project Overview

This project develops a prediction model for finding fast growing firms. We build 3 different prediction models (logit, LASSO, Random Forest) to identify firms that belong in the top 25th percentile of sales revenue growth between 2012 and 2014 .

---

## Repository Structure

```
assignment2/
├── code/
├── data/
│   ├── raw/                          # Original data from cs_bisnode_panel
│   └── clean/                        # Processed data
├── output/                           # Figures and tables
└── README.md
```

---

## Data Source
cs_bisnode_panel.csv 
From the case studies data repo. 

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

1. Open and run `code/01_data_prep_fast_growth.ipynb` (to prepare dataset for prediction)
2. Open and run `code/02_predicting_fast_growth.ipynb` (TASKS 1 - prediction using the full sample)


- **Approximate run time**: 
`code/01_data_prep_fast_growth.ipynb` ~ 1 min
`code/02_predicting_fast_growth.ipynb` ~ 15 mins
---


## Results Summary

1. Executive Summary: See `output/ececutive_summary.pdf`  
2. Technical Summary: See `output/technical_summary.pdf`  


---

## AI Usage Disclosure

AI (Claude) was used for:
- Code generation and debugging
- Code refactoring
- Documentation formatting

All outputs were verified and validated by the authors.

---

## References

- Békés, G. & Kézdi, G. (2021). *Data Analysis for Business, Economics, and Policy*. Cambridge University Press.
