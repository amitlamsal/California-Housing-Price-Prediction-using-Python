# California Housing Price Prediction
### Multiple Linear Regression Analysis | Python | Statsmodels | Webster University

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![Statsmodels](https://img.shields.io/badge/Statsmodels-3776AB?style=flat&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=flat&logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-1D9E75?style=flat)

---

## Project Overview

This project builds and evaluates multiple linear regression models to predict housing prices based on key property attributes. Three models were developed, compared and evaluated using statistical metrics — R², Adjusted R², AIC and BIC — with the best model selected and validated through rigorous diagnostic testing.

**Course:** Statistical Analysis | Webster University

---

## Dataset

| Attribute | Detail |
|---|---|
| **File** | Housing_Dataset.csv |
| **Variables** | Price, Area, Bedrooms, Bathrooms, Stories, Air Conditioning, Parking |
| **Target Variable** | Price (housing price) |
| **Preprocessing** | Air conditioning converted from Yes/No to binary 0/1 |

---

## Project Workflow

### 1. Data Import and Exploration
- Loaded dataset into pandas DataFrame
- Checked data types and identified categorical variable (airconditioning)
- Converted airconditioning from Yes/No to binary 0/1
- Generated summary statistics using `df.describe()`

### 2. Visual Exploration
- Seaborn pairplot showing relationships between all variables
- Individual scatter plots of each independent variable against price

### 3. Three Regression Models Built

| Model | Variables Included | Purpose |
|---|---|---|
| **Model 1** | Area, Bedrooms, Bathrooms | Base model |
| **Model 2** | Area, Bedrooms, Bathrooms, Stories | Extended model |
| **Model 3** | Area, Stories, Air Conditioning, Parking | Alternative model |

### 4. Model Comparison and Selection

Models compared using four metrics:

| Metric | Model 1 | Model 2 | Model 3 |
|---|---|---|---|
| R² | Lower | **Highest** | Lower |
| Adjusted R² | Lower | **Highest** | Lower |
| AIC | Higher | **Lowest** | Higher |
| BIC | Higher | **Lowest** | Higher |

**Model 2 selected** — highest R² and Adjusted R² with lowest AIC and BIC.

### 5. Statistical Diagnostic Tests on Model 2

| Test | Purpose | Result |
|---|---|---|
| **VIF** | Multicollinearity check — variables should not be correlated with each other | Checked against threshold of 5 |
| **Residual scatter plot** | Homoskedasticity check — variance should be constant | Visually inspected |
| **Residual histogram** | Normality check — residuals should be normally distributed | Mean approximately 0 |
| **Breusch-Pagan test** | Formal heteroskedasticity test | p-value evaluated at 0.05 |
| **Influence plot (Cook's Distance)** | Outlier detection | Extreme outliers identified |

### 6. Predictions
Created 5 hypothetical observations with varying property attributes and used `results2.predict()` to generate estimated housing prices.

---

## Key Findings

- **Model 2** (Area + Bedrooms + Bathrooms + Stories) is the best performing model based on R², Adjusted R², AIC and BIC
- **Multicollinearity** — VIF checked for all independent variables against threshold of 5
- **Heteroskedasticity** — Breusch-Pagan test applied to formally test for non-constant variance
- **Outliers** — Influence plot revealed some extreme data points that affect model fit
- **Parking and Air Conditioning** variables showed slightly diagonal residual patterns suggesting potential model limitations

---

## Tools and Libraries

| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning and manipulation |
| `numpy` | Numerical operations |
| `statsmodels` | OLS regression, VIF, Breusch-Pagan, Durbin-Watson, RESET test |
| `matplotlib` | Base plotting |
| `seaborn` | Pairplots, scatter plots, regression plots |
| `scipy.stats` | Shapiro-Wilk normality test |

---

## Repository Structure
```
california-housing-price-prediction/
│
├── Housing_Price_Prediction.ipynb    ← Main Jupyter notebook
├── Housing_Dataset.csv               ← Housing dataset
└── README.md
```
---

## How to Run

1. Clone the repository:
```bash
git clone https://github.com/amitlamsal/California-Housing-Price-Prediction-using-Python
```

2. Install required libraries:
```bash
pip install pandas numpy statsmodels matplotlib seaborn scipy
```

3. Open the notebook:
```bash
jupyter notebook Housing_Price_Prediction.ipynb
```

---

## Education Context

| Detail | Info |
|---|---|
| **Course** | Statistical Analysis |
| **University** | Webster University, St. Louis MO |
| **Program** | MS Business Analytics |

---

## About the Author

**Amit Lamsal**
MS Business Analytics — Webster University, St. Louis MO


[![LinkedIn](https://img.shields.io/badge/LinkedIn-amitlamsal-0077B5?style=flat&logo=linkedin)](https://www.linkedin.com/in/amitlamsal)
[![Email](https://img.shields.io/badge/Email-amitlamsal72@gmail.com-D14836?style=flat&logo=gmail)](mailto:amitlamsal72@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-amitlamsal-181717?style=flat&logo=github)](https://github.com/amitlamsal)
