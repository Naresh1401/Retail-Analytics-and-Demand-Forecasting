# 📊 Retail Analytics & Demand Forecasting

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![Prophet](https://img.shields.io/badge/Prophet-Time_Series-green.svg)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

End-to-end retail demand forecasting pipeline using **Facebook Prophet** with holiday effects and hyperparameter optimization. Analyzes 178K+ retail orders to forecast product demand for inventory planning and supply chain optimization.

---

## Problem Statement

- **Dataset**: 178,150 retail orders with delivery, product, and customer data
- **Goal**: Forecast next 24 months of demand for the top-selling product
- **Challenge**: 55% late delivery rate necessitates accurate demand planning

## Approach

### 1. Exploratory Data Analysis
- Delivery risk analysis across shipping modes
- Product frequency and revenue ranking
- Customer segment profiling
- Late delivery pattern identification

### 2. Feature Engineering
- Extracted time-based features: Year, Month, Day, Weekday from shipping dates
- Label encoding and one-hot encoding for categorical variables
- Identified top product: **Product ID 365** (Perfect Fitness's Perfect Rip Deck)

### 3. Time Series Forecasting with Prophet
- Built Prophet model with US & Puerto Rico holiday effects
- Generated **730-day (2-year)** demand forecast with uncertainty intervals
- Cross-validation with **MAPE** (Mean Absolute Percentage Error)

### 4. Hyperparameter Tuning
- Grid search over **250+ combinations**:
  - `seasonality_mode`: additive / multiplicative
  - `seasonality_prior_scale`: controls flexibility of seasonality
  - `holidays_prior_scale`: controls holiday effect strength
  - `changepoint_prior_scale`: controls trend changepoints

---

## Project Structure

```
Retail-Analytics-and-Demand-Forecasting/
├── Retail_Analytics_and_Demand_Forecasting.ipynb   # Main analysis & forecasting
├── Holidays_code.ipynb                              # US/PR holiday data generator
├── US-Pr-Holidays.xlsx                              # Holiday reference data (2015–2021)
└── README.md
```

---

## Key Results

- Stable increasing demand pattern predicted for top product over 24 months
- Holiday effects significantly impact demand (Thanksgiving, Christmas, Black Friday)
- Multiplicative seasonality outperforms additive for this product category
- Optimized model achieves low MAPE on cross-validation

---

## Tech Stack

| Component | Technology |
|-----------|-----------|
| Language | Python |
| Forecasting | Facebook Prophet |
| Data Processing | pandas, NumPy |
| ML | scikit-learn |
| Visualization | Matplotlib, Seaborn |
| Holiday Data | `holidays` library |

---

## Quick Start

```bash
pip install pandas numpy scikit-learn prophet matplotlib seaborn holidays openpyxl
jupyter notebook Retail_Analytics_and_Demand_Forecasting.ipynb
```

---

## Author

**Naresh Sampangi**

## License

This project is licensed under the MIT License.